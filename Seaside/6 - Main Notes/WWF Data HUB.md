

https://docs.google.com/document/d/1kkMv3kRgoy90mkfLL6wy-k9zHedmQfeZem6d5hwQVqs/edit?tab=t.0#heading=h.gwpmxeny1xu

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