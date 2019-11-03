## [Youtube - Laravel + MySql con Docker Despliegue a Produccion - Jesus Matíz](https://youtu.be/q7v2Qqf2Vmk)

### Comandos básicos:
```js
//borrar todos los contenedores
docker rm -f $(docker ps -aq)

//borrar todas las imagenes
docker rmi -f $(docker images -aq)

//construyendo la imagen y levantando los contenedores con esta imagen
docker-compose up -d

//accediendo por bash MINGW64
winpty docker exec -it e057 //bin//bash

//accediendo por bash cmder
//docker exec -it e057 /bin/bash
```

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
  # servicio 1: La base de datos
  serv-mysql:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: db_killme
      MYSQL_USER: userfull
      MYSQL_PASSWORD: userfull
    ports:
      # puerto externo: puerto interno
      - 3306:3306
    volumes:
      - E:/projects/docker/databases/mysql_3.7/schemas:/var/lib/mysql
    networks:
      laravel_prod_net:
        ipv4_address: 173.22.100.9

  # servicio 2: La instalación de apache
  serv-laravel:
    build:
      # context: de donde se va a recuperar la configuración para la instalación
      context: ./
      dockerfile: dockerfile
    ports:
      - 8200:80
    volumes:
      - ./example-prod:/var/www/
      - ./example-prod/public:/var/www/html
    networks:
      laravel_prod_net:
        ipv4_address: 173.22.100.10
    # depends_on indica que se cree primero la bd (servicio 1)
    depends_on:
      - serv-mysql

# se confirman los volumenes
volumes:
  example-prod:  # carpeta ./example-prod
  database:      # carpeta E:/projects/docker/databases/mysql_3.7/schemas
networks:
  laravel_prod_net:
    driver: bridge
    ipam:
      driver: default
      config:
        - 
          subnet: 173.22.100.0/24
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
  ...
  Successfully built 34cb9f31d6a4
  Successfully tagged jesus_matiz_laravel_laravel-prod:latest
  WARNING: Image for service laravel-prod was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
  Creating jesus_matiz_laravel_laravel-db_1 ... done
  Creating jesus_matiz_laravel_laravel-prod_1 ... done
  ```
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/1029x117/f59cbe9b236dfe04a5946d5451f9d8e6/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5db43f16df811534517445ec/9ef401a42f3e99506fc5bfe72729f5a2/image.png)
  - Veo un problema: El mysql tiene un tamaños de 210 MB recien instalado. Si esto se hace para cada imágen se me dispararía el espacio en disco.

- **docker exec -it e057 /bin/bash**
  - En **cmder** va ok
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/417x225/5b7ce272a66e71913472112bada3f4cd/image.png)
  - En **MINGW64** va mal
  ```js
  //este ocurre en MINGW64 (terminal de git)
  $ docker exec -it e057 /bin/bash
  the input device is not a TTY.  If you are using mintty, try prefixing the command with 'winpty'

  //se soluciona agregando winpty y doble barra a bin/bash => //bin//bash
  $ winpty docker exec -it e057 //bin//bash
  root@e057e2ee35cc:/var/www/html#
  ```