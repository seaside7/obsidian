
### 1. Find project location

```
find / -maxdepth 3 -type d -iname "*katingan*"
```

Purpose:

- locate actual Laravel project folder


### 2. Check permissions

```
ls -lals -ld ...
```

Purpose:

- see if folder writable
- detect suspicious `dr-xr-xr-x`

Meaning:

```
d = directoryr = readw = writex = execute/access
```

This:

```
dr-xr-xr-x
```

means:

- nobody can write

### 3. Change permission

```
chmod 775
```

Purpose:

- allow owner/group write access

---

### 4. Test GitLab runner access

```
sudo -u gitlab-runner touch ...
```

Purpose:

- simulate CI/CD behavior
- confirm runner really can write

Before fix:

```
Permission denied
```

---

### 5. Use `stat`

```
stat folder
```

Purpose:

- see REAL permission accurately

We discovered:

```
775
```

became:

```
555
```

again automatically.

That meant:

- some process kept changing permissions back.
### 6. Find suspicious processes

```
ps aux | grep ...
```

Purpose:

- inspect background running processes

We found:

```
php /projects/katingan-revamp/public/wp-admin/css/wp/79/097823
```

Huge red flag because:

- Laravel app normally runs via php-fpm
- not random standalone hidden php scripts

### 7. Kill malware process

```
kill -9 1795
```

Purpose:

- force stop malicious process

After killing it:  
permissions stopped reverting.

That confirmed:

- the malware was the cause.
This command is just **searching active processes**:

```
ps aux | grep -E "chmod|chown|inotify|gitlab|deploy|supervisor|cron" | grep -v grep
```

Meaning one by one:

```
ps aux
```

Shows all running processes on the server.

```
grep -E "chmod|chown|inotify|gitlab|deploy|supervisor|cron"
```

Filters only lines containing these keywords:

```
chmod      process changing permissionschown      process changing ownershipinotify    process watching file changesgitlab     GitLab runner/deploy relateddeploy     deployment scriptssupervisor background process managercron       scheduled jobs
```

```
grep -v grep
```

Hides the grep command itself from the result.

So the purpose was:

```
Find any process that may be automatically changing folder permission back to 555.
```



Most likely: yes, this was an actual compromise attempt / malware activity on the server.

Not a “virus” like Windows desktop virus, but more likely:

```
PHP webshell / backdoor malware
```

Meaning:

- attacker uploaded malicious PHP script
- script runs commands on server
- can modify files/permissions
- can maintain persistence
- can open remote access

Why I’m confident:

1. Your Laravel app suddenly had:
    
    ```
    public/wp-admin/css/wp/79/097823
    ```
    
    which is fake WordPress-looking structure.
    
2. A standalone PHP process was running:
    
    ```
    php /projects/.../097823
    ```
    
    Normal Laravel apps DO NOT do this.
    
3. Folder permissions kept reverting automatically to:
    
    ```
    555
    ```
    
    after you manually changed them.
    
4. After killing PID 1795:
    
    ```
    permission stopped reverting
    ```
    
    That directly links the process to the behavior.
    

So yes:

```
this was malicious behavior
```

But:

```
we don't yet know:- how attacker entered- whether more backdoors exist- whether credentials leaked- whether database affected
```




## Step 1 — make Laravel files non-writable

Run:

```
find /projects/katingan-revamp -type d -exec chmod 755 {} \;
```

Then:

```
find /projects/katingan-revamp -type f -exec chmod 644 {} \;
```

Then restore writable runtime folders:

```
chmod -R 775 /projects/katingan-revamp/storage /projects/katingan-revamp/bootstrap/cache
```