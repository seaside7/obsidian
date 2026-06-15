

kl mau nambahin remote url, pake profile yg udh diset di config

git remote add github git@wwf-github:wwfinternational/datahub-fe.git


buat test connectionnya

ssh -T wwf-github


kl mau pull dari specific branch di gitlab / github

git fetch github

Merge GitHub’s development branch into your local staging, local branchnya staging

git merge github/development

kl mau push branch development di github tp dri branch staging

git pull github development

git push github staging:development


windows
ls ~/.ssh

cat C:\Users\Seaside\.ssh\id_ed25519.pub



curl -v "https://api-datahub-nonprod-api-dev.azurewebsites.net/v2/data-npo/cards?year=2025"

mac:
git clone git@catalyze-git:catalyzecommunications/katingan-project-revamp.git

test connection
ssh -T catalyze-git


# What you must do

Create **a new SSH key for this repo**.

### 1️⃣ Generate new key

Run:

ssh-keygen -t ed25519 -C "giswebapi" -f ~/.ssh/id_giswebapi

You will get:

~/.ssh/id_giswebapi  
~/.ssh/id_giswebapi.pub

---

### 2️⃣ Copy the public key

cat ~/.ssh/id_giswebapi.pub

Copy the whole line.

---

### 3️⃣ Add deploy key to the repo

Go to:

GISWebAPI  
Settings → Deploy Keys

Click **Add deploy key**

Paste the key.

Enable:

Allow write access

(if you need push)

---

### 4️⃣ Add SSH config entry

Edit:

~/.ssh/config

Add:

Host giswebapi  
  HostName github.com  
  User git  
  IdentityFile ~/.ssh/id_giswebapi  
  IdentitiesOnly yes

---

### 5️⃣ Clone using alias

git clone git@giswebapi:wwfinternational/GISWebAPI.git