## [Youtube - Laravel + MySql con Docker Despliegue a Produccion - Jesus Matíz](https://youtu.be/q7v2Qqf2Vmk)

- [**`docker-compose up -d`**](https://youtu.be/q7v2Qqf2Vmk?t=1217)
  - **-d** interactivo
  - Puede que de un error: Pool overlaps with oter one on this address space
  - Se debe a que otro contenedor está usando esta ip
- [**`docker exec -it 7430 /bin/bash`**](https://youtu.be/q7v2Qqf2Vmk?t=1424)
  - Entra de modo interactivo al contenedor

## Files

### docker-compose.yml
```yml
version: "3.7"
services:
  laravel-db:
    image: mysql:5.7
    enviroment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: db_chalan
      MYSQL_USER: eaf
      MYSQL_PASSWORD: eaf123
    ports:
      # puerto host:puerto contenedor
      - 33069:3306
    volumes:
      - E:\projects\docker\databases\mysql_3.7:/var/lib/mysql
    networks: 
      latavel_prod_net:
        ipv4_address: 172.21.100.9
latavel-prod:
  build:
    context: ./
    dockerfile: dockerfile
  ports:
    - 8200:80
  volume:
    - E:\projects\prj_elchalanaruba:/var/www/
    - E:\projects\prj_elchalanaruba\the_public:/var/www/html
  networks: 
      latavel_prod_net:
        ipv4_address: 172.21.100.10
  depends_on:
    # puntero a item anterior
    - laravel-db
volumes:
  example-prod:
  database:
networks:
  laravel_prod_net:
    driver: bridge
    ipam:
      driver: default
      config:
        - 
          subnet: 172.21.100.0/24
```
### dockerfile
```yml
FROM php:7.3-apache

RUN apt-get update                                  \
    && apt-get install -y                           \
    && docker-php-ext-install mysqli pdo pdo_mysql  \
    && a2enmod rewrite                              \
    && chmod 777 -R -c /var/www
```
### Prueba concepto 03/11/2019
```js
// he ejecutado en esta misma carpeta:
docker build .
...
Successfully built 34cb9f31d6a4
SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. All files and directories added to build context will have '-rwxr-xr-x' permissions. It is recommended to double check and reset permissions for sensitive files and directories.
```
```js
//ERROR
λ docker-compose up -d
ERROR: The Compose file '.\docker-compose.yml' is invalid because:
Unsupported config option for services.laravel-db: 'enviroment'
services.laravel-db.ports contains unsupported option: '33069'
```