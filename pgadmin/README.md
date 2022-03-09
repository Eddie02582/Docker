# pdAdmin4

download image
```
    docker pull dpage/pgadmin4
```

## environment 

<a href = "https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html">官網</a>


### PGADMIN_DEFAULT_EMAIL
This is the email address used when setting up the initial administrator account to login to pgAdmin. This variable is required and must be set at launch time.


### PGADMIN_DEFAULT_EMAIL
This is the password used when setting up the initial administrator account to login to pgAdmin. This variable is required and must be set at launch time.

##Example

```
docker run -p 5050:80 \
    -v D:\Docker\pgAdmin-data:/var/lib/pgadmin \
    -e PGADMIN_DEFAULT_EMAIL=eddie_chuang@sercomm.com \
    -e PGADMIN_DEFAULT_PASSWORD=password \
    -e PYTHONPATH=/pgadmin4 \
    -d dpage/pgadmin4 \
    -name 'pgadmin'  
 ```
 
 
 
 ## BackUP Data
 
 
 ```
 docker exec  6fde2520e1c8 /usr/local/pgsql-14/pg_dump postgresql://postgres:password@10.10.63.171:5432/postgres  --verbose --format=c --blobs  > qq.backup
 ```
 
 或者進入CLI
``` 
    /usr/local/pgsql-14/pg_dump postgresql://postgres:password@10.10.63.171:5432/postgres --file "/var/lib/pgadmin/storage/eddie_chuang_sercomm.com/qq.back_up" --verbose --format=c --blobs
```
 
 
 