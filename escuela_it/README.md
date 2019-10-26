# [Youtube - Curso docker](https://www.youtube.com/watch?v=X0lFXKSjjxk&feature=youtu.be)
  - [escuela.it/cursos/curso-docker/](https://register.gotowebinar.com/recording/recordingView?webinarKey=1386177801230585859&registrantEmail=eacevedof%40yahoo.es)

## Capitulo 01
- Docker. 
  - Solución de contenedores
  - Los contenedores son entornos pequeños controlados
  - Es proyecto de código abierto que permite **automatizar el despliegue de apps dentro de contenedores**
  - Permite la **virtualización de apps** en múltiples sistemas operativos.

- Contenido del curso:
  - **Qué es Docker?**
  - **Comandos Docker**
    - Veremos algunos comandos básicos de docker
  - **Dockerfile**
    - Crearemos los primeros docker file
  - Docker Compose
    - Nos va a permitir unir varios contenedores y orquestarlos para crear una solución mucho más compleja
    - Ejemplo de la solución, contenedores y sus responsabilidades:
      - Backend
      - Base de datos
      - Otra solución para micro servicios
  - Volúmenes de Docker
  - Network en Docker
    - Puertos que vamos a escuchar en un contenedor
    - Configurar restricciones para unas ips para escuchar unas y otras no
  - Construcción de entornos con múltiples imágenes de Docker
    - Nos apoyaremos en docker compose
  - Node en Docker
  - Ambiente MEAN en Docker
  - Creando pipeline CI/CD con Docker
  - Paso a producción de Docker
  - Usando gitlab ^^ para tus pipelines
  - Consideraciones de Seguridad
  - Herramientas útiles que puedes usar con Docker

## Qué es Docker?
- Empaquetaremos todo en un contenedor
- Ubuntu
- Alpy
- Dependencias
### Porque ayuda?
- Que pasa si actualizo un servidor 
- En mi pc funciona
- Se trabaja con el mismo entorno que en prod
#### Maquinas virtuales vs Docker
- ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/556x291/3c4f9c634ae255f11820e2569f708eed/image.png)
- Una VM se podría traducir en un Contenedor
- **Servidor físico con VM**
  - Sistema operativo independiente de cada VM
  - Hypervisor (gestor de vm)
  - VM1,...,VMn
    - Para cada Vi
    - Sistema operativo independiente del físico
    - Bin/Labs
    - App-i
  
- **Servidor físico con Docker**
  - Sistema operativo (compartido con los contenedores)
  - **Docker Engine**
  - Container-1,...,Container-n
    - Para cada Container-i
    - Bin/Labs
    - App-i
- En cada servidor que tenga **docker engine** se podrá desplegar cualquier **imágen** de docker
- La imágen va ser todo el empaquetado de lo que se desea desplegar (tanto la app con las reglas de negocio como las libs, servicios y apps propias de infraestructura) y se va a poder desplegar multiples veces
- Cuando la **imágen** esta desplegada le llamarémos **contenedor**
- [La naturaleza de cada app]https://youtu.be/X0lFXKSjjxk?t=1083) nos indicará los requerimientos tanto de infraestructura como de lógica de negocio que necesitaremos para generar la imágen.

## [Yb - Como funciona docker o como se generan las imágenes?](https://youtu.be/X0lFXKSjjxk?t=1137)
- ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/1030x407/73647653a48c94de637110e214d7e75a/image.png)
- **capas**
  - Necesitaremos python 3.7, se obtiene del repo de imágenes [Docker Hub](https://cloud.docker.com/repository/list)
  - A partir de esta imágen base, se puede agregar componentes y/o servicios que se necesiten en la app
  - Ejemplo: Posgres, nginx, etc...
    ```js
    FROM python: 3.7
    RUN apt-get install -g postregsql
    RUN apt-get install -g nginx
    RUN pip install -r requirements.txt
    ```
  - Cada una de estas instrucciones (de instalación de los serv anteriores) se ejecutarán por capas
  - Todas estas instrucciones terminarán formando una **receta**

- **Preguntas**
  - Se puede reutilizar el mismo Dockerfile en distintos proyectos?.
    - Si, en dockerhub
  - Las apps necesitan requerimientos especificos para docker?
    - No, es suficiente declarar los requerimientos en la **receta**
    - Para desarrollo trabajaremos con un volumen. (mapeo carpeta loc ruta en el contenedor)
    - [De esta forma](https://youtu.be/X0lFXKSjjxk?t=1525) haremos nuestros cambios, hacemos el build de la app (como si hicieramos un pseudo despliegue en prod) dentro del contenedor.
    - Versionamos el contenedor.
  - Cada contenedor tendra sus dependencias de forma independiente, esto no implica el consumo de más recursos?
    - Se puede gestionar cada contendor de forma aislada con sus propios recursos.
  - [Contenedores, imágenes y volumen:](https://youtu.be/X0lFXKSjjxk?t=1720)
    - Al definir un docker file, definimos las instrucciones que generan una imágen.
    - Cuando al docker-file le hago docker build se convierte una imágen
    - Cuando a la imagen le hago docker run se convierte en un contenedor.
    - **`docker file => docker build => imagen => docker run => contenedor`**
    - Para bases de datos tendremos que montar volumenes, ya que apenas se para el contenedor no hay datos.
### [Yb - Dockerfile](https://youtu.be/X0lFXKSjjxk?t=1929)
```js
FROM ubuntu:19.10

RUN mkdir /code

# con WORKDIR se le indica a la imagen que arranque en esta ruta
WORKDIR /code

RUN apt-get update

RUN apt-get install -y nginx
RUN echo "Hello World"

# con ADD se pasa al contenedor
ADD example.sh /code/
ADD start_app.sh /code/

RUN chmod -x example.sh

RUN ./example.SH
```
- Preguntas
  - [Se tiene que descargar la img antes de ejecutar Dockerfile o se descargará automaticamente?](https://youtu.be/X0lFXKSjjxk?t=2238)
    - Se descarga al ejecutar el **Dockerfile**
    - Las lineas de las recetas se van a convertir en una img con un tag
    - Se almacenará en local pero tendría la posibilidad de compartirla en dockerhub
  - [Instalación de extension de Docker](https://youtu.be/X0lFXKSjjxk?t=2319)
  - [Software malicioso en imagenes?](https://youtu.be/X0lFXKSjjxk?t=2347)
    - Abrimos la receta, el [**Dockerfile** en github](https://github.com/docker-library/mysql/blob/6659750146b7a6b91a96c786729b4d482cf49fe6/8.0/Dockerfile), podremos revisar las instrucciones
    - Se recomienda usar las recetas oficiales.
  - [Puedo migrar mi infra a docker?](https://youtu.be/X0lFXKSjjxk?t=2414)
    - Directamente no.
    - Habría que definir los paquetes (en Dockerfile)
## Comandos Docker
- [Trello](https://trello.com/b/xxK10wBd/docker)
- **error:** No me va `docker build .`.  Creo que es pq no tengo activado **Hyper-V**
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/927x363/cef6621c24efa5d32c18411e442e8fac/image.png)
  - [Porque Docker necesita Hyper-V en windows?](https://stackoverflow.com/questions/48251703/if-docker-runs-natively-on-windows-then-why-does-it-need-hyper-v)
- [**`docker build .`**](https://youtu.be/X0lFXKSjjxk?t=2707)
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/574x426/5e6cc7d73544e7c88a4f896305417d60/image.png)
- [**`docker images`**](https://youtu.be/X0lFXKSjjxk?t=2868)
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/864x256/84fbab463eb11d11af51fba7da277125/image.png)
- [**`docker run -it <IMAGE ID> bash`**](https://youtu.be/X0lFXKSjjxk?t=2892)
  - **-it** da permisos para entrar en el contenedor y que permaneza de forma interactivo
  - bash el comando que se va a ejecutar dentro de contenedor.
  - con esto ya se **inicia sesión** en el contenedor ^^
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/339x73/d2ca10dcf8d56cb4cce1344c7e578619/image.png)
- [**`docker ps -a`**](https://youtu.be/X0lFXKSjjxk?t=3066)
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/1181x136/a8769c67b7c9c1b9662d26c8b750c52e/image.png)
  - Como no hay nada ejecutandose dentro del contenedor al salirnos (con exit) este se detiene.
  - Status EXITED
  - Cada vez que se lanza un contenedor se vuelve al punto inicial de la imagen.
- [**`docker rm <tag contenedor>`**](https://youtu.be/X0lFXKSjjxk?t=3238)
  - Elimino los contenedores que no se están usando
- [**`docker build . --tag example:1 --no-cache`**](https://youtu.be/X0lFXKSjjxk?t=3328)
  - **--no-cache** indica que no se va a usar de la cache. Reconstruye desde 0, por ejemplo cuando se cambia algo en el **Dockerfile**
- [Se puede hacer algo para que el cont no se cierre?](https://youtu.be/X0lFXKSjjxk?t=3398)
  - Si, cuando tenga un servicio permanente en el contenedor automaticamente no se cerrara.
- [**`docker rm <hash>|<name>`**](https://youtu.be/X0lFXKSjjxk?t=4035)
  - Esto dará error si el contenedor sigue corriendo
- [**`docker rm -f <hash>|<name>`**](https://youtu.be/X0lFXKSjjxk?t=4127)
  - Fuerza el borrado aunque este corriendo el contenedor
- [**`docker rm -f $(docker ps -aq)`**](https://youtu.be/X0lFXKSjjxk?t=4178)
  - Elimina todos los contenedores. `$(docker ps -aq)` extrae los *CONTAINER ID*
- [**`docker images`**](https://youtu.be/X0lFXKSjjxk?t=4189)
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/866x357/4efe086feb13cfd163c2dba99a6c43c3/image.png)
  - Pueden llenar nuestro disco duro, asi que las podemos ir eliminando.
- [**`docker rmi <IMAGE ID>**](https://youtu.be/X0lFXKSjjxk?t=4228)
  - Una vez eliminada la imagen eliminara todas sus dependencias
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/715x283/e8b4f2e3f57c0459b3ce22790a86db90/image.png)
  - Es importante ir limpiando el sistema sobretodo cuando versionamos imagenes y lo desplegamos en producción.
- [**``**]()
- [**``**]()
- [**``**]()
- [**``**]()


