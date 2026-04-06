

livewire update, katinganmentanya.com, 

![[Pasted image 20260326112906.png]]

![[Pasted image 20260326112922.png]]



Katingan Problem

## What was going wrong (simple version)

You actually had several separate issues stacked together.

### 1. Livewire JavaScript (`livewire.js`) returned 403

- The browser asked for `/livewire/livewire.js`.
- On your server, that request did not work reliably (PHP/Laravel path + nginx setup).
- We copied Livewire’s real JS files into `public/vendor/livewire/` and added nginx rules so:
    - `/livewire/livewire.js` and `/livewire/livewire.min.js` are served directly as files (not through the fragile PHP route).

So: same URL the page uses, but nginx hands out the file from disk.

### 2. Clicking “Buy Carbon Credit” still broke: 403 + “Maintenance”

- That was not Cloudflare and not normal Laravel errors.
- Old files were still on disk: `storage/framework/maintenance.php` and `storage/framework/down` (leftovers from `php artisan down` or a similar deploy).
- Laravel loads `maintenance.php` before the app starts. It showed a tiny page: “403 Forbidden” + “Maintenance”.
- Normal pages could still work if they were on the “except” list in that maintenance config, but `POST /livewire/update` was not, so only Livewire actions hit the maintenance wall.

Fix: delete those two files (and/or run `artisan up`). After that, bare `curl` POST to `/livewire/update` showed 419 — that’s normal without a browser session/CSRF token — and in the real browser, Livewire works (your modal).

### 3. Why we used Docker (`docker exec ...`)

- On the server, `php` is not installed for `root` on the host; PHP runs inside the `php-fpm-8` container.
- So commands like `php artisan ...` must run inside that container, e.g.  
    `docker exec php-fpm-8 php /projects/katingan-revamp/artisan ...`

### 4. Why we edited nginx inside the `nginx` container

- Ports 80/443 are handled by the `nginx` container (Nginx Proxy Manager), not by nginx on the host.
- Config lives under `/data/nginx/...` in that container; we added `/data/nginx/custom/server_proxy.conf` so your rules survive until you change them.

### 5. `curl` commands you saw

- `curl -sI "http://127.0.0.1/..." -H "Host: katinganmentaya.com"`  
    = “Ask your own server for this URL, pretending the site name is katinganmentaya.com” (same vhost as the real site).
- `-sI` = only headers, quiet. Used to see 200 vs 403 quickly.

---

## Short “what to remember”

|Problem|Cause|Fix (idea)|
|---|---|---|
|`livewire.js` 403|JS URL not served reliably|Copy assets to `public/vendor/livewire/` + nginx aliases for `/livewire/*.js`|
|Button → 403 “Maintenance”|Stale `maintenance.php` / `down`|Remove them / `artisan up`|
|Commands “don’t work” on SSH|PHP is in Docker|Use `docker exec php-fpm-8 php ... artisan ...`|

If `maintenance.php` / `down` ever come back, the same “Maintenance” behaviour can return — usually someone ran `php artisan down` or a deploy script left files behind. `php artisan up` and clearing those files fixes it.

I can also add a one-line note to your internal runbook (what to run after deploy: copy Livewire assets, don’t leave `down` on production) if you want that written down for the team.