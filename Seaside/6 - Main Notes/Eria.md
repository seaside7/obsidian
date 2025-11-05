
php artisan serve --host=127.0.0.1 --port=8080

 http://localhost:8080/backend-login for admin
admin_eria
6bTXLs9G9a#y

home page

carousel terlalu development banget, harusnya slideshow banner


![[Pasted image 20251004212302.png]]

title subtitle description button (redirect)



asean 3 harusnya ky gni
![[Pasted image 20251004212552.png]]

![[Pasted image 20251004213653.png]]

url messed

harusnya

![[Pasted image 20251004213718.png]]
set routes





![[Pasted image 20251006143734.png]]

yg baru dirom disni


untuk setup admin lama disni
![[Pasted image 20251006143834.png]]![[Pasted image 20251006143844.png]]

![[Pasted image 20251006144244.png]]


controllernya disni



contoh intro

The current homepage uses the static partial resources/views/frontend/homepage/intro.blade.php, which hardcodes that paragraph.

The old, DB-driven section still exists in resources/views/frontend/homepage/about.blade.php. It renders from tb_home_about via $about = HomeAbout::first() in the controller.

![[Pasted image 20251006161014.png]]

![[Pasted image 20251006161547.png]]



home page
 intro 4 hours

asean 3 map add admin dynamic 1hr

show to locationv2.blade 1hr

- change route path
- location change to asean+3, routenya


feature projects: 2 jam

kl gnti2 vue, harus npm run dev, to compile


- Yes. npm run dev compiles and then watches for changes. Once you see “compiled successfully,” you can stop it (Ctrl+C) if you don’t need live rebuilds.

- If you stop it, the latest build stays in public/js/app.js, so php artisan serve will use it fine.

- If you want auto-rebuilds as you edit Vue files, keep npm run dev running in a separate terminal while php artisan serve runs in another.

- {{ ... }} escapes HTML before output. If the value contains <p>…</p>, it will print the tags as text (safe for user content).

- {!! ... !!} outputs the value unescaped. Any HTML inside is rendered by the browser (so your editor’s <p>, <strong>, etc. become real markup).

We use {!! ... !!} here because you’re intentionally storing rich HTML from the admin editor and want it rendered on the page, just like “Introduction.”



<a href="{{ route('frontend.project') }}" class="d-none d-md-inline btn btn-outline-warning m-none">VIEW ALLss PROJECTS</a>


staging link disni: https://rkcmpd-eria.staging.catalyze.id/our-projects






funding explorer

![[Pasted image 20251016194110.png]]

![[Pasted image 20251016194225.png]]


eria itu paten logonya


sliding banner -> carousel


feature collection

![[Pasted image 20251022143121.png]]



tabbed pages: pages with sidebar
![[Pasted image 20251030112636.png]]

