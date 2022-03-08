# pdAdmin4

download image
```
    docker pull dpage/pgadmin4
```

## environment 

<a href = "https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html">©xºô</a>


### PGADMIN_DEFAULT_EMAIL
This is the email address used when setting up the initial administrator account to login to pgAdmin. This variable is required and must be set at launch time.


### PGADMIN_DEFAULT_EMAIL
This is the password used when setting up the initial administrator account to login to pgAdmin. This variable is required and must be set at launch time.

##Example

```
docker run -p 5050:80 \
    -e PGADMIN_DEFAULT_EMAIL=your_email \
    -e PGADMIN_DEFAULT_PASSWORD=password \
    -e PYTHONPATH=/pgadmin4 \
    -d dpage/pgadmin4 \
    -name 'pgadmin'\
 ```