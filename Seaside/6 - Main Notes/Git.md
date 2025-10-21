

kl mau nambahin remote url, pake profile yg udh diset di config

git remote add github git@wwf-github:wwfinternational/datahub-fe.git


buat test connectionnya

ssh -T wwf-github


kl mau pull dari specific branch di gitlab / github

git fetch github

Merge GitHub’s development branch into your local staging, local branchnya staging

git merge github/development

kl mau push branch development di github tp dri branch staging

git push github staging:development


windows
ls ~/.ssh

cat C:\Users\Seaside\.ssh\id_ed25519.pub