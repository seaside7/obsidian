

https://docs.google.com/document/d/1kkMv3kRgoy90mkfLL6wy-k9zHedmQfeZem6d5hwQVqs/edit?tab=t.0#heading=h.gwpmxeny1xu

https://datahub.staging.catalyze.id/

https://datahub.staging.catalyze.id/?bypass=true


cms.data.panda.org

[admin@catalyze.id](mailto:admin@catalyze.id) secret1234 atau secret1234!

cms:
admin@catalyze.id 
secret1234

arcgis api, jlnin di local
docker compose -f docker-compose.dev.yml up arcgis -d --build

trs cek
curl http://localhost:8000/health


(Invoke-WebRequest -Uri "https://api.ipify.org").Content  
Test-NetConnection 172.205.217.96 -Port 27017 
ip pc wwf-prod: 180.252.92.213
username: said_admin
password: Seaside11


set env:
basedurl: https://maps.panda.org/portal/
tilelayer: [https://tiles.arcgis.com/tiles/RS8mqPfEEjgYh6uG/arcgis/rest/services/Robinson_basemap/MapServer/0](https://tiles.arcgis.com/tiles/RS8mqPfEEjgYh6uG/arcgis/rest/services/Robinson_basemap/MapServer/0)
webmapid: 9ceb58b818ff4405a2732d264cf9262b


mongodb atlas:
said
Seaside11

mongodump --uri "mongodb+srv://said:Seaside11@clusterazure-prod.el3npp.mongodb.net/datahub-nonprod" --archive="C:\Temp\datahub-nonprod.archive" --gzip

(Invoke-WebRequest -Uri "https://api.ipify.org").Content

ip address



db: mongodb

staging is replicate production, 

we develop 

build error
Issue  

- Build failed previously due to strict Next/Image domain checks and inconsistent API URL resolution (fallback to a staging URL when env was absent).

Fix  

- Allowed remote images in next.config.mjs so Next/Image no longer blocks the build.
- Exposed NEXT_PUBLIC_API_URL from environment only; removed the hardcoded staging fallback.
- Centralized URL resolution in getApiBaseUrl() so all fetchers use the same env-based base URL and log clearly if it’s missing. (this code is in src/service/api.js




![[Pasted image 20251013190552.png]]



mongodb compass

Seaside11@

using email


test directly

curl https://datahub-api.staging.catalyze.id/v2/partials/navigation





# Check what NEXT_PUBLIC_API_URL is set to in production
echo $NEXT_PUBLIC_API_URL

# Then test with the actual backend URL
curl -v "<THE_BACKEND_URL_FROM_ABOVE>/files/WWF%20NETWORK%20DATAHUB_staging/banner-homepage-4-mobile-1760588611646.jpg"

# Also test the Azure API (same as staging if it's pointing to the same backend)
curl -v "https://api-datahub-nonprod-api-dev.azurewebsites.net/files/WWF%20NETWORK%20DATAHUB_staging/banner-homepage-4-mobile-1760588611646.jpg"



the api is worlking, but the image not
![[Pasted image 20251026115447.png]]



pull staging catalyze for about us



filter problem:

### What Went Wrong:

1. Filter API Bug (Line 148 in tag-groups.service.ts):

Before (WRONG):

id: it._id?.toString?.() || it.item_id || '',  // Used array element _id

After (FIXED):

id: it.item_id || '',  // Use stable item_id

Impact: When the admin panel fetched filter options to display dropdowns, it received the array element _id instead of the correct item_id.

---

2. Admin Panel Flow:

When someone created or updated a resource through the admin panel:

1. ✅ Admin panel fetches filters → Gets _id: "68fb28e911786adb13caf3d3"

2. ✅ User selects "Andreas Birnstingl"

3. ❌ Admin panel saves: tag_groups: [{ items: ["68fb28e911786adb13caf3d3"] }]

4. ❌ Should have saved: tag_groups: [{ items: ["68e64849ba9c46076abd4072"] }]

---

3. Why Two Different IDs Exist:

MongoDB automatically generates _id for array elements when you do operations like $push. The item_id field was probably:

- Added later as a design improvement

- Or manually generated with a different algorithm

- Or came from a different system/migration

This created a mismatch where:

- Array element _id = 68fb28e911786adb13caf3d3

- Stable item_id = 68e64849ba9c46076abd4072

---

## 🎯 Timeline of How It Happened:

1. Initial Setup: TagGroups created with both _id and item_id fields

2. Bug Introduced: Filter API returned array _id instead of item_id

3. Data Corruption: Every time resources were created/updated via admin panel, wrong IDs were saved

4. Filter Failure: When users tried to filter, they used item_id (correct), but resources had _id (wrong) → No match!

---

## ✅ What We Fixed:

1. Migration: Updated all 7 resources to use correct item_id values (35 IDs fixed)

2. API Fix: Changed filter API to return item_id as the id field

3. Prevention: Now the system consistently uses item_id throughout

---

Lesson: When you have two similar ID fields (_id and item_id), always use the stable, intentional one (item_id) for references, not the auto-generated MongoDB array element _id! 🎓


mongodb
said_admin
hUsabBfpdIp7P3sf



resources sm ky visual libraries, tp bedanya dia pny glossary, resources ga pnya , data owner etc, bikin dibikin di tag groups




![[Pasted image 20251111193651.png]]


ketika masuk page detail api buat ngitung view blm ada


featured resorces ga berhasil ke save di module training, ga ngesave atau ga ngereturn, padahal dkirimnyha sama ky yg dipages



GET /partials/resources?route=resources&resourceType=POLICIES&page=1&limit=6&sort_field=&sort_direction=-1

GET /partials/filters?resourceType=POLICIES

GET /api/proxy?path=v2/resource/{slug}




visual libraris related files, wktu diclick ga muncul, done


simple power bi test, 


shortcut pdf kaya related file



kl diclick yg bawah2 semuanya ke click


di policies wktu save tag groups ga bsa