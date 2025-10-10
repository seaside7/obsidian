

**Akun Distrios**

  

  

  

production

distrios_ptlarisandalanindonesiahub@gmail.com

DistriosDLHUB

  

  

staging distibutor :

distrios_ptmandalakrisnautama@manuva.com

Distriosmandala

  

  

  

superadmin staging:

admin.distribution@tjetak.com

superadminstaging

  

  

admin staging:

[zepan@mail.com](mailto:zepan@mail.com)

Zepanadmin

  

  

  

  

  

ga ada sih, td cm ingetin amal untuk pembayaran travelelo

  

  

okaay sudah diinfoin ke ak ya kak, td info dari Kak Amal lusa kemungkinan, tp besok ku kabari lg kak

  

udah diinfo nominal dan due datenya hari ini,

  

  

salesapp

lottedepok@gmail.com

Lottedepok

  

restrukturisasi@rbt.id

  

superadmin production:

[tomi.permana@tjetak.com](mailto:tomi.permana@manuva.com)  
manuvatomtom

  

finance :

email : farhadsupply@manuva.com

pass : farhadsupply

  

const downloadUrl = `${API_URL}distribution-order/collections/order-payment-report?${params.toString()}`;

  

  

mkdir smallbiz-be && cd smallbiz-be && npm init -y && npm install lambda-api mongodb jsonwebtoken bcryptjs uuid dotenv && touch index.js src/routes.js src/db.js src/middleware/auth.js

  

  

  

  

const URI = 'distribution-order/graphql';

  

  

[http://dashboard-staging.tjetak.com/](http://dashboard-staging.tjetak.com/)

  

  

  

**CV-20250919-1758245904817**

MDI/ORD/DIST/20259/0028

MDI/ORD/DIST/20259/0027

  

MDI/ORD/DIST/20257/0089

  

  

          mutation UploadTempFile($file: UploadFileInput!, $context: String!) {

            uploadTempFile(file: $file, context: $context) {

              file_url

              uploaded_at

              file_name

            }

          }

ini contoh graphql upload file:

```

mutation UploadTempFile {

  uploadTempFile(

    file: {

      name: "front-store-photo.jpg"

      base64: "/9j/4AAQSkZJRgABAQEAYABgAAD/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSopGR8tMC0oMCUoKSj/2wBDAQcHBwoIChMKChMoGhYaKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCj/wAARCAABAAEDASIAAhEBAxEB/8QAFQABAQAAAAAAAAAAAAAAAAAAAAv/xAAUEAEAAAAAAAAAAAAAAAAAAAAA/8QAFQEBAQAAAAAAAAAAAAAAAAAAAAX/xAAUEQEAAAAAAAAAAAAAAAAAAAAA/9oADAMBAAIRAxEAPwCdABmX/9k="

    }

    context: "submission-front"

  ) {

    file_url

    uploaded_at

    file_name

  }

}```