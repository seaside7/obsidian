

[https://abnj.staging.catalyze.id/](https://abnj.staging.catalyze.id/)  (ini untuk fe)
abnj-be.staging.catalyze.id/admin/auth/login

token:
55b7b0ff9d4521f13e7167a86d6b0ac539ef1c40466bfac2749da96fffc4996bc5f1bb884468270f875d2567a907e165812803e7aba951deea2506d7cc5eb3cedc0e3052c4c00967522a4106e0a5d42bf948b959ae0a5c92ca8417002885894960fcccd11e33dc85f287cea54e03f4dd4228493e4a88f96743fac1854d96f2b6

𝑺𝒆𝒙𝒕𝒂𝒑𝒆-𝑨𝒍𝒕𝒆𝒓-𝑺𝒌𝒂𝒏𝒅𝒂𝒍-𝑯𝒊𝒋𝒂𝒃-𝑳𝒆𝒏𝒈𝒌𝒂𝒑-𝑳𝒂𝒏𝒄𝒂𝒓-𝑺𝒕𝒓𝒆𝒂𝒎𝒊𝒏𝒈-𝑫𝒂𝒏-𝑫𝒐𝒘𝒏𝒍𝒐𝒂𝒅-19-11.1587087/page-37#post-1913429356

arekmoal
Takanome88


user : catalyze pass : catalyze

strapi login
```
url : https://abnj-be.staging.catalyze.id/admin/auth/login
email : analytics@catalyzecommunications.com
password : WkyLcptqclhFn6v
```
/𝙃𝙚𝙖𝙙𝙨𝙚𝙩-𝙍𝙚𝙦𝙪𝙞𝙧𝙚𝙙-yang-ada-desahan-dan-percakapan-saja-desember-asyikk.1591020/page-3

https://vide.ws/e/arrk8jfh9l66?path=e&id=arrk8jfh9l66
https://vide.ws/e/h49hqpn0b5ta?path=e&id=h49hqpn0b5ta
https://vide.ws/e/m1e07a9ukwbb?path=e&id=m1e07a9ukwbb
https://vide.ws/e/bl8nymdi97sg?path=e&id=bl8nymdi97sg
https://vide.ws/e/hi1frwgfu7vy
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


home page: 

navigas gpp dihardcode

# **home introduction**
![[Pasted image 20251013171847.png]]
cb cek button learn morenya, learn morenya kayanya di fe hardcoded

 ini settingan di strapinya
![[Pasted image 20251013183813.png]]


# **knowledge center**
(repository of macem2 business case) 

dibagi menjadi 3, yg more to come ini buat backup klo2 ada coming soon

ini blm ada copywritingnya, baru layoutnya

![[Pasted image 20251013172112.png]]

ada find business cases button, nah bsa ga tuh ada ada checkbox buat coming soon, atau gw kirim flag ke fe, 1 and 2, kl 2 itu coming soon, kl coming soon ga bsa dihover

kl staging skrg ky gni

![[Pasted image 20251013172230.png]]

kayanya cmsnya udh bisa bikin card ky gni:
![[Pasted image 20251013172413.png]]


terus dibagian ini:
![[Pasted image 20251013172443.png]]

skrg harus ada title sub title plus ada button yg connect  ke find  businss case (halaman indexnya)
![[Pasted image 20251013172523.png]]




![[Pasted image 20251013174739.png]]

bagian ini sm ky about us section, ada birunya ada contentnya ada buttonya "fiind funding"
tp ada gmbr2nya, ada 4 gambar, upload 4 logo, bsa upload .svg



![[Pasted image 20251013174937.png]]
latest update udh ada, ga perlu ngapa2in, ad button view all, cb cek doang aja, skrg blm ada


![[Pasted image 20251013175004.png]]



faq di home page, ada 3, lalu ada view all, nnt nyambung ke halaman faq, yg ada 20 faq, 

![[Pasted image 20251013175059.png]]

udh ada faq building yg ada di home page, di cms udh ada

![[Pasted image 20251013175138.png]]

tp ga tau caranya gmn nampilin yg 3 di home page, gmn metodenya
 

Working API Endpoints (all functional, tested):

- GET /api/homepage/about-us - About Us section

- GET /api/homepage/knowledge-center - Knowledge Center with cards

- GET /api/homepage/find-funding - Find Funding with partners

- GET /api/homepage/news - News section with curated articles

- GET /api/homepage/faq - FAQ section with curated FAQs 

expo-jaksel-include-room-abg-new-comers-body-goals-toge-dc-promo-gunpit-700k-good-service-gfe-13-oktober-25-oktober-kemang.1583766/
# resources



samain ky sub nya knowledge center - greenshipping
tp bedanya kl di greenshipping ada button introduction dan business cases, di resources ada introduction dan tools

![[Pasted image 20251015142759.png]]




Funding explorer

each filter has their own parameter            




## Step 3: Display Funds in the Frontend

In your frontend application (React/Next.js), you'll make API calls:

### Get the Funding Explorer page content:

const response = await fetch('http://localhost:3048/api/funding-explorer');

const pageData = await response.json();

// Use pageData.data.title, pageData.data.description, etc.



### 

Get all funds with logos:

const response = await fetch('http://localhost:3048/api/funds');

const fundsData = await response.json();

// fundsData.data will be an array of all funds

fundsData.data.forEach(fund => {

  console.log(fund.Title);

  console.log(fund.logo); // This will include the image URL

  console.log(fund.regions);

  console.log(fund.instruments);

});


### The logo URL structure:

When you upload a logo, Strapi returns the image details. The logo field will look like:

{

  "logo": {

    "id": 1,

    "url": "/uploads/edf_logo_123.png",

    "formats": {

      "thumbnail": { "url": "/uploads/thumbnail_edf_logo_123.png" }

    }

  }

}

Use it in your frontend like:

Great questions! Let me explain how filters and search work with the Strapi API:

## 1. Filters (Project Type, Instruments, Region, Funding Range)

Strapi provides built-in filtering through query parameters. Since we have these fields in the Fund schema, you can filter them directly:

### Example Filter Queries:

Filter by Region:

GET /api/funds?filters[regions][$contains]=Africa

Filter by Funding Range:

GET /api/funds?filters[fundingRange][$eq]=Over 10 million

Filter by Fund Type:

GET /api/funds?filters[fundType][$eq]=  Public Financing

Multiple Filters (AND logic):

GET /api/funds?filters[regions][$contains]=Africa&filters[fundingRange][$eq]=Over 10 million

### In Your Frontend (React/Next.js):

const [filters, setFilters] = useState({
  projectType: '',
  instruments: '',
  region: '',
  fundingRange: ''
});

const fetchFunds = async () => {
  let url = 'http://localhost:3048/api/funds?';
  
  // Add filters to query
  if (filters.region) {
    url += `filters[regions][$contains]=${filters.region}&`;
  }
  if (filters.fundingRange) {
    url += `filters[fundingRange][$eq]=${filters.fundingRange}&`;
  }
  if (filters.instruments) {
    url += `filters[instruments][$contains]=${filters.instruments}&`;
  }
  if (filters.projectType) {
    url += `filters[eligibleProjectTypes][$contains]=${filters.projectType}&`;
  }
  
  const response = await fetch(url);
  const data = await response.json();
  return data.data;
};


## 2. Search Functionality

Strapi also provides built-in search using the $contains or $containsi (case-insensitive) operators:

### Search by Title:
GET /api/funds?filters[Title][$containsi]=ocean

### Search Multiple Fields (OR logic):

GET /api/funds?filters[$or][0][Title][$containsi]=ocean&filters[$or][1][description][$containsi]=ocean&filters[$or][2][issuer][$containsi]=ocean

const [searchQuery, setSearchQuery] = useState('');

const searchFunds = async (query) => {
  const url = `http://localhost:3048/api/funds?filters[$or][0][Title][$containsi]=${query}&filters[$or][1][description][$containsi]=${query}&filters[$or][2][issuer][$containsi]=${query}`;
  
  const response = await fetch(url);
  const data = await response.json();
  return data.data;
};



## 3. Sort Functionality (A-Z)

For the sort dropdown:

Sort A-Z (ascending):

GET /api/funds?sort=Title:asc

Sort Z-A (descending):

GET /api/funds?sort=Title:desc

---

## Complete Frontend Example:

import { useState, useEffect } from 'react';

function FundingExplorer() {
  const [funds, setFunds] = useState([]);
  const [searchQuery, setSearchQuery] = useState('');
  const [filters, setFilters] = useState({
    projectType: '',
    instruments: '',
    region: '',
    fundingRange: ''
  });
  const [sortOrder, setSortOrder] = useState('asc');

  const fetchFunds = async () => {
    let url = 'http://localhost:3048/api/funds?';
    
    // Add search
    if (searchQuery) {
      url += `filters[$or][0][Title][$containsi]=${searchQuery}&`;
      url += `filters[$or][1][description][$containsi]=${searchQuery}&`;
      url += `filters[$or][2][issuer][$containsi]=${searchQuery}&`;
    }
    
    // Add filters
    if (filters.region) {
      url += `filters[regions][$contains]=${filters.region}&`;
    }
    if (filters.fundingRange) {
      url += `filters[fundingRange][$eq]=${filters.fundingRange}&`;
    }
    if (filters.instruments) {
      url += `filters[instruments][$contains]=${filters.instruments}&`;
    }
    if (filters.projectType) {
      url += `filters[eligibleProjectTypes][$contains]=${filters.projectType}&`;
    }
    
    // Add sort
    url += `sort=Title:${sortOrder}`;
    
    const response = await fetch(url);
    const data = await response.json();
    setFunds(data.data);
  };

  useEffect(() => {
    fetchFunds();
  }, [searchQuery, filters, sortOrder]);

  return (
    <div>
      {/* Search */}
      <input 
        type="text" 
        placeholder="Search for funding..."
        value={searchQuery}
        onChange={(e) => setSearchQuery(e.target.value)}
      />
      
      {/* Filters */}
      <select onChange={(e) => setFilters({...filters, region: e.target.value})}>
        <option value="">All Regions</option>
        <option value="Africa">Africa</option>
        <option value="Europe">Europe</option>
        <option value="Asia">Asia</option>
      </select>
      
      <select onChange={(e) => setFilters({...filters, fundingRange: e.target.value})}>
        <option value="">All Ranges</option>
        <option value="Under 1 million">Under 1 million</option>
        <option value="Between 1-10 million">Between 1-10 million</option>
        <option value="Over 10 million">Over 10 million</option>
      </select>
      
      {/* Sort */}
      <select onChange={(e) => setSortOrder(e.target.value)}>
        <option value="asc">A-Z</option>
        <option value="desc">Z-A</option>
      </select>
      
      {/* Display Funds */}
      <div className="funds-grid">
        {funds.map(fund => (
          <div key={fund.id} className="fund-card">
            {fund.logo && (
              <img src={`http://localhost:3048${fund.logo.url}`} alt={fund.Title} />
            )}
            <h3>{fund.Title}</h3>
            <p>{fund.issuer}</p>
            <p>{fund.description}</p>
          </div>
        ))}
      </div>
    </div>
  );
}


Here are the curl commands to test - just copy and paste:

1. Test the filters endpoint:

curl http://localhost:3048/api/funds/filters

2. Test getting all funds:

curl http://localhost:3048/api/funds

3. Test search (search for "ocean"):

curl "http://localhost:3048/api/funds?filters[\$or][0][Title][\$containsi]=ocean"

4. Test filter by region (Africa):

curl "http://localhost:3048/api/funds?filters[regions][\$contains]=Africa"

5. Test filter by funding range:

curl "http://localhost:3048/api/funds?filters[fundingRange][\$eq]=Over 10 million"

6. Test sort A-Z:

curl "http://localhost:3048/api/funds?sort=Title:asc"

7. Test multiple filters (region + funding range):

curl "http://localhost:3048/api/funds?filters[regions][\$contains]=Europe&filters[fundingRange][\$eq]=Over 10 million"

---

Make sure your Strapi server is running first! If not, run:

npm run develop

Then wait for it to start, and try the curl commands above! 🚀

curl http://localhost:3048/api/funds/filters



prefix menu homepage

resource masukin pages aja, 

jgn menu sendiri

field tools udh ada di category

related links


fundiong explorer pake pages aja


GET /api/pages?filters[slug][$eq]=knowledge-centre
GET /api/pages?filters[slug][$eq]=resources


Invoke-RestMethod -Uri "http://localhost:3048/api/funding-explorer" -Method GET | ConvertTo-Json -Depth 4

get funding explorer page with all filter and fund


Invoke-RestMethod -Uri "http://localhost:3048/api/funds/jkddxrgatf1nh5oi5fsnge25" -Method GET | ConvertTo-Json -Depth 4

get specific funf


$uri = "http://localhost:3048/api/funding-explorer"; $body = @{ 'instruments[]' = @('s7k9g4sf0ljdk01wuoyr28kq', 'w3n8eaqf5lmpp2it7b6p5er2'); 'regions[]' = 'qa0m38t02rdt8641e0kes23o'; 'projectTypes[]' = 't0v7lnztqwrman3zjoi2kua3'; 'sortBy' = 'alphabetical'; 'pagination[page]' = 1; 'pagination[pageSize]' = 10 }; Invoke-RestMethod -Uri $uri -Method GET -Body $body | ConvertTo-Json -Depth 3

http://localhost:3048/api/funds/compare?fund1=jkddxrgatf1nh5oi5fsnge25&fund2=fwyy2e8w6p854xlfpvsmp2zk&fields=fundType,fundSubtype,issuer,fundingRange,instruments,regions



funding size content remove

geography itu ganti jd Region Description

example f5

about the issuer content remove

ganti env staging server

# 1. SSH into staging
ssh user@staging.catalyze.id

# 2. Navigate to project
cd /projects/abnj-be

# 3. Edit .env file
nano .env
# Change: NODE_ENV=staging → NODE_ENV=development

# 4. Restart container
docker compose restart staging

# 5. Go to admin panel and configure Edit View
# https://abnj-be.staging.catalyze.id/admin
# Settings → Content-Type Builder → Fund → Configure the view → Edit View

# 6. Change back .env
nano .env
# Change: NODE_ENV=development → NODE_ENV=staging

# 7. Restart again
docker compose restart staging



128.199.157.158

[10:49 AM](https://chat.catalyze.id/catalyze/pl/c1b1tkbfhjbbbefshh7nio6q1r)

port : 22 user : root pass : ssh_key

old
159.89.192.157



exclude category tools, 

tp di resources harus ada tools


fundint explainer


## Correct URLs for Funding Explorer:

### Sort Funds by Title:

A-Z (Ascending):

https://abnj-be.staging.catalyze.id/api/funding-explorer?sortBy=a-z&pagination[page]=1&pagination[pageSize]=9

or

https://abnj-be.staging.catalyze.id/api/funding-explorer?sortBy=alphabetical&pagination[page]=1&pagination[pageSize]=9

Z-A (Descending):

https://abnj-be.staging.catalyze.id/api/funding-explorer?sortBy=z-a&pagination[page]=1&pagination[pageSize]=9

### Sort Funds by Date:

Newest First:

https://abnj-be.staging.catalyze.id/api/funding-explorer?sortBy=latest&pagination[page]=1&pagination[pageSize]=9

Oldest First:

https://abnj-be.staging.catalyze.id/api/funding-explorer?sortBy=a-z&pagination[page]=1&pagination[pageSize]=9


telemetry  grafana

Seaside11


![[Pasted image 20251113142749.png]]


![[Pasted image 20251114155919.png]]


Invoke-RestMethod -Uri "https://abnj-be.staging.catalyze.id/api/global" -Method GET | ConvertTo-Json -Depth 10


disclaimer text sampign fund card title
page about

/konten-igo-pilihan-skandal-kolpri-talent-alter-hijab-chindo-vcs-vcapk-streaming-and-download-no-quote-no-req-08-12-2025.1591924/page-2#post-1913534092