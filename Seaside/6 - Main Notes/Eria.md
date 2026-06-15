
php artisan serve --host=127.0.0.1 --port=8080

 http://localhost:8080/backend-login for admin
admin_eria
6bTXLs9G9a#y

prod:
U : catalyze_admin 
P : 58b283ccabe2!!



git checkout --theirs public/

git add public/

git commit -m "Resolve merge conflicts by accepting incoming changes"



![[Pasted image 20260402115245.png]] 


ini yg key highlight


![[Pasted image 20260406133042.png]]


in filter if no data no need to show in here



tabbed pages status published and draft di 1st tier 2nd tier


wktu bikin tabbed pages perlu ada parent dropdown ambil dari header

http://127.0.0.1:8080/epr/static

static


check chmod
ls -ld /projects



This:

```
drwxr-xr-x
```

means permission `755`.

Breakdown:

```
d rwx r-x r-x│ │   │   ││ │   │   └── others│ │   └────── group│ └────────── owner└──────────── directory
```

Numeric mapping:

```
r = 4w = 2x = 1
```

So:

Owner:

```
rwx = 4+2+1 = 7
```

Group:

```
r-x = 4+0+1 = 5
```

Others:

```
r-x = 4+0+1 = 5
```

Final:

```
755
```

Meaning:

- owner can read/write/execute
- others can only read/enter
- safer than `777`

For `/projects`, this prevents everyone from freely writing there.