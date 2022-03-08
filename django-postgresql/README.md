# Django Postgresql


```
django-postgresql-|
                  |---- demo
                  |----- docker-compose.yml
                  |------ Dockerfile
                  |------ requirements.txt
                  |
```




## docker-compose
```
version: "3.9"
   
services:
  db:
    image: postgres:latest
    restart: unless-stopped
    volumes:
      - ./data/db:/var/lib/postgresql/data
    environment:
      POSTGRES_USER: Eddie
      POSTGRES_DB: postgres
      POSTGRES_PASSWORD: password
    ports:
      - "5432:5432"
  web:    
    build: .
    command: python manage.py runserver 0.0.0.0:8000
    volumes:
      - ./demo:/code
    ports:
      - "8000:8000"
    environment:
      POSTGRES_USER: Eddie
      POSTGRES_DB: postgres
      POSTGRES_PASSWORD: password
    depends_on:
      - db
      
```
## docker-compose

```
FROM python:3.6-bullseye
ENV PYTHONUNBUFFERED 1
WORKDIR /code
COPY ./demo /code/
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
```



## django 
不知道為什麼postgres沒建立USER:Eddie
setting.py
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'postgres',
        'USER': 'postgres',
        'PASSWORD': 'password',
        'HOST': 'db',
        'PORT': 5432,
    }
}
```

##


```
django-postgresql-|
                  |---- demo
                  |----- docker-compose.yml
                  |------ Dockerfile
                  |------ requirements.txt
                  |---- data
```


















