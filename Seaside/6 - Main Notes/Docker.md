

docker exec -i mysql_ctz mysqldump -uroot -proot --no-create-info abnj faqs > D:\Coders\catalyze\faq_table_data.sql

docker cp "D:\path\to\abnj.sql" mysql_ctz:/tmp/abnj.sql


docker cp ~/Downloads/abnj.sql mysql_ctz:/tmp/abnj.sql



## ✅ Step 3. Import into the database

Now execute this:

`docker exec -it mysql_ctz sh -c "mysql -u root -proot abnj < /tmp/abnj.sql"`



## ✅ Step 4. Verify import

Check if the database and tables were created successfully:

`docker exec -it mysql_ctz mysql -u root -proot -e "SHOW DATABASES;" docker exec -it mysql_ctz mysql -u root -proot -e "USE abnj; SHOW TABLES;"`



Invoke-WebRequest -Uri "http://localhost:3048/api/homepage/faq" -UseBasicParsing -Method HEAD