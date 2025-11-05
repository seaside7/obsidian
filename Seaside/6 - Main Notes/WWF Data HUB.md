

https://docs.google.com/document/d/1kkMv3kRgoy90mkfLL6wy-k9zHedmQfeZem6d5hwQVqs/edit?tab=t.0#heading=h.gwpmxeny1xu

https://datahub.staging.catalyze.id/

https://datahub.staging.catalyze.id/?bypass=true

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

![:+1:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-small/1f44d.png)1


![[Pasted image 20251013190552.png]]



mongodb compass

Seaside11@

using email


test directly

curl https://datahub-api.staging.catalyze.id/v2/partials/navigation



## 🎯 The Problem:

The non-working domain is trying to fetch images from:

https://api-datahub-nonprod-api-dev.azurewebsites.net/files/...

But this URL is likely:

1. Not accessible from the frontend server

2. Requires authentication

3. Has CORS restrictions

4. Returns 404 or other errors

test the api directly

curl https://api-datahub-nonprod-api-dev.azurewebsites.net/files/WWF%20NETWORK%20DATAHUB_staging%2Fbanner-homepage-4-1760588597956.jpg





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