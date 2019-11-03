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
    # será equivalente a: http://localhost:8200/
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

//tenía mal la palabra enviroment. es "enviroNment" ^^
```
- Ahora funciona:
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5db43f16df811534517445ec/b029c21a9b7184f354ead3845138f04a/image.png)
  ```js
  E:\projects\prj_docker\jesus_matiz_laravel (master -> origin)
  λ docker-compose up -d
  Creating network "jesus_matiz_laravel_laravel_prod_net" with driver "bridge"
  Creating volume "jesus_matiz_laravel_example-prod" with default driver
  Creating volume "jesus_matiz_laravel_database" with default driver
  Pulling laravel-db (mysql:5.7)...
  5.7: Pulling from library/mysql
  80369df48736: Pull complete
  e8f52315cb10: Pull complete
  cf2189b391fc: Pull complete
  cc98f645c682: Pull complete
  27a27ac83f74: Pull complete
  fa1f04453414: Pull complete
  d45bf7d22d33: Pull complete
  c7d49ffebc56: Pull complete
  511a8052b204: Pull complete
  5d5df4c12444: Pull complete
  d482603a2922: Pull complete
  Digest: sha256:44b33224e3c406bf50b5a2ee4286ed0d7f2c5aec1f7fdb70291f7f7c570284dd
  Status: Downloaded newer image for mysql:5.7
  Building laravel-prod
  Step 1/2 : FROM php:7.3-apache
  ---> d04b0f5fdc60
  Step 2/2 : RUN apt-get update                                      && apt-get install -y                               && docker-php-ext-install mysqli pdo pdo_mysql      && a2enmod rewrite
              && chmod 777 -R -c /var/www
  ---> Using cache
  ---> 34cb9f31d6a4

  Successfully built 34cb9f31d6a4
  Successfully tagged jesus_matiz_laravel_laravel-prod:latest
  WARNING: Image for service laravel-prod was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
  Creating jesus_matiz_laravel_laravel-db_1 ... done
  Creating jesus_matiz_laravel_laravel-prod_1 ... done
  ```
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/1029x117/f59cbe9b236dfe04a5946d5451f9d8e6/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5db43f16df811534517445ec/9ef401a42f3e99506fc5bfe72729f5a2/image.png)
  - Veo un problema: El mysql tiene un tamaños de 210 MB recien instalado. Si esto se hace para cada imágen se me dispararía el espacio en disco.

### Comandos básicos:
```js
docker-compose up -d
//borrar todos los contenedores
docker rm -f $(docker ps -aq)
//borrar todas las imagenes
docker rmi -f $(docker images -aq)
```