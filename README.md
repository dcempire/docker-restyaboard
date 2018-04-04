**Warning:** This image is not maintained anymore. I personally switched to [Wekan](https://wekan.io/).

# viossat/restyaboard
开源程序，基于Restya平台，类似Trello的看板系统
源码从# viossat/restyaboard 扩展而来，采用了restyaboard 0.6.3的源码，PHP 版本从5.0升到了7.0
Open source, Trello like Kanban board, based on Restya platform.
http://restya.com/board

## `docker-compose.yml`

```
restyaboard:
  image: dcempire/restyaboard:0.6.3
  ports:
    - "80:80"
  volumes: # optional
    - /volume/path/media:/var/www/html/media
  links:
    - postgres
    - elasticsearch # optional
  environment:
    - DB_HOST=postgres
    - DB_PORT=5432 # optional, default: 5432
    - DB_USER=restyaboard
    - DB_PASSWORD=restyaboard # optional, default: DB_USER
    - DB_NAME=restyaboard # optional, default: restyaboard
postgres:
  image: postgres
  volumes: # optional
    - /volume/path/postgres:/var/lib/postgresql/data
  environment:
    - POSTGRES_USER=restyaboard
    - POSTGRES_PASSWORD=restyaboard
elasticsearch: # optional
  image: elasticsearch
  volumes: # optional
    - /volume/path/elasticsearch:/usr/share/elasticsearch/data
```

## Default users

```
Username: admin
Password: restya

Username: user
Password: restya
```
