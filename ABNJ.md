

[https://abnj.staging.catalyze.id/](https://abnj.staging.catalyze.id/)  (ini untuk fe)
abnj-be.staging.catalyze.id/admin/auth/login

user : catalyze pass : catalyze


bikin branch baru 
pull ke development
pull ke  staging

![[Pasted image 20251009154808.png]]

ini category,

cardnya (aggregating demain) di knowledge,
![[Pasted image 20251009154907.png]]

knp dia taro di knowledge 1 to many nya, krn 1 knowledge bsa nempel ke bbrp category


![[Pasted image 20251009155125.png]]

kl ini pagenya, itu knowledge center ada di page


![[Pasted image 20251009155313.png]]

ini homepage untuk susunan di home page,



![[Pasted image 20251009155749.png]]

funding explorer taxonomy


9 october 2025
Here’s a concise recap of what we changed and why.

Code edits

- src/api/funding-explainer/controllers/funding-explainer.ts

- Added controller action plain to fetch the single-type and return only { title, subtitle, content }.

- src/api/funding-explainer/routes/funding-explainer.ts

- Replaced the core router with a custom route so GET /api/funding-explainer maps to funding-explainer.plain and shows no query params in Swagger.

- src/api/funding-explainer/routes/funding-explainer-plain.ts

- Added an auxiliary route file for a minimal GET at /api/funding-explainer/plain (kept for flexibility; main path now uses the minimal action).

- src/extensions/documentation/documentation/1.0.0/full_documentation.json

- Updated servers[0].url from http://0.0.0.0:3048/api to http://localhost:3048/api to fix Swagger “Failed to fetch”.

CMS (Strapi Admin) changes

- Content-Type Builder: created Single Type “Funding Explainer”; fields set to:

- title (Text), content (Rich text – Markdown). Optionally subtitle (Text).

- Removed the old body Text field.

- Content Manager: added and Published the entry.

- Settings → Roles → Public: enabled permission for Funding-explainer → plain (GET).

Result

- New minimal public endpoint: GET /api/funding-explainer

- Returns only required fields: { title, subtitle, content }.

- No pagination/sort query params in Swagger for this route.

- Swagger now uses localhost and requests succeed (after enabling Public permission and publishing content).