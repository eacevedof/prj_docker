## Indice

## Sección 1: Introducción al curso
- [Udemy](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/3963868#overview)

### [7 Maquina Virtual UBUNTU 16.04 con Docker](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9671966#overview)
- [onedrive](https://onedrive.live.com/?authkey=%21ANAqKS%5FsyP3u2Os&id=2F5823B4594339C3%2116706&cid=2F5823B4594339C3)
### [8 Instalar Docker en Centos](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9625748#overview)
- [pdf](https://a2.udemycdn.com/2018-03-15_10-17-37-b55782c603d5ecd0cc007432116aa550/original.pdf?nva=20191110205206&download=True&filename=1-Practicas-Docker.Instalar-Centos.pdf&token=0e65864f2497f13cb7d83)
### [9. Instalar docker en Ubuntu (Debian-Suse-....)](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9625754#overview)
- [pdf](https://a2.udemycdn.com/2018-03-15_12-00-07-c828045b1e55c53fbf9ebd5d08b00c09/original.pdf?nva=20191110205502&download=True&filename=1-Practicas-Docker-Instalaci-n-Ubuntu.pdf&token=0206a9031e45c95fb822b)
### [10. Prácticas. Instalación en Linux: Centos y Ubuntu](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9678418#overview)
- [pdf](https://a2.udemycdn.com/2018-03-15_10-17-37-b55782c603d5ecd0cc007432116aa550/original.pdf?nva=20191110205206&download=True&filename=1-Practicas-Docker.Instalar-Centos.pdf&token=0e65864f2497f13cb7d83)
### [11. Instalar Docker en Windows Parte 1](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626120#overview)
- Docker Toolbox está desactualizada
### [12. Instalar Windows en Docker Parte 2](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626858#overview)
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/396x244/ae59381db77f38adcb816fc81e6a4604/image.png)
- Windows containers y linux container
- Si trabajamos con windows containers es mas eficiente ya que no tiene que montar un Hyper-V con Moby que es el emulador linux
- No se podían ejecutar en paralelo los Windows y los Linux, se debe seleccionar uno.
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/418x444/c40058eaaa53018ed385c57a7b6cab65/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/731x604/51fa5b1e1548dad8b74a50c75ce2a714/image.png)
- Los contenedores windows sirven para instalar servicios windows. 
  - IIS, SSIS, .Net, Outlook, OneDrive, etc
### [13. Arquitectura de Docker. Imágenes, Containers y daemons](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626128#overview)
- Ya tenemos instalado el **Docker Host y el Docker Client**
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/585x286/dba4144953bc8054599905505003bacc/image.png)
- Docker Host
- Docker Daemon
- Docker Client
  - Hace llamadas REST al Daemon
  - Pull, Push, Run
- Imagenes:
  - Plantilla de solo lectura
  - Los contenedores se crean a partir de estas

## Sección 2: Trabajar con contenedores

### [14. Arrancar y parar Docker](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626140#overview)
- **`dockerd`** arrancar el daemon.
- En windows no funciona
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/489x61/f11d116eacf7eaa707515ec2380bc5f5/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/945x194/317aab0408072eaf0746baf0f439a263/image.png)
  - Habría que usar la app de docker instalada para levantar este servicio
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/336x69/10b92ce8030d6dcdffa152f719a1001d/image.png) 
- **`docker ps`** muestra el listado de contenedores

### [15. Prácticas con Arranque y parada de Docker](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9678000)
- [Practica](https://a2.udemycdn.com/2018-03-15_14-50-42-4b352139a9c59ff669055d2759d7167b/original.pdf?nva=20191110214945&download=True&filename=3-Arrancar-y-parar-los-servicios-docker.pdf&token=034f3b5844f88d12498c6)
```sh
# centos
docker version
ps -ef | grep docker
systemctl start Docker
systemctl status docker
systemctl enable docker
```
### [16. Crear nuestro primer contenedor](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626148)
- **docker run hello-world**
  - crea un contenedor basado en una plantilla
  - busca la imagen hello-world en local
  - no la encuentra, la busca y descarga de Docker Hub
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/830x61/f1c354600a140110c8c788ac0106860d/image.png)
### [17. Ver imágenes y contenedores Parte 1](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626180)
- **docker images**
- **docker ps**
  - no muestra nada porque el contenedor que hemos arrancado se ha parado
- **docker ps -a**
  - `-a` todo (all)
  - muestra los contenedores detenidos 
  - **Exited (0)** es que se ha parado correctamente
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/923x71/0193e3491218e4b1b188ed5104e9e84c/image.png)

### [18. Ver imágenes y contenedores Parte 2](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626186)
- **docker ps -n 7** listado limit 7 Los ultimos 7 contenedores sobre los que se ha operado
- **docker ps -a -q** listado de ids
- **docker ps -a -n 3 -s** listado ultimos 3 con su tamaño (-s)
- **docker ps -a -f "name=<some name>"** listado con where name='some name'
- **docker images**
- **docker images -q**
### [19. Práctica. Primeros pasos con contenedores](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9685168#questions)
- [pdf practicas](https://a.udemycdn.com/2018-03-16_08-31-28-0ff693fad42beee2453cba8ce991f1d9/original.pdf?nva=20191110230129&download=True&filename=4-Visualizar-informaci-nde-contenedores-e-imagenes.pdf&token=03ff577d75ebc55b97bfd)
- **docker run -it ubuntu bash**
  - **i**: interactive, **t**: terminal
  - Monta un contenedor de ubuntu y accede por shell
- **docker run busybox**
- **docker ps**
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1080x99/20a0b941a0c4d9bba1f08a6ac5be1deb/image.png)
- **docker ps -a -f name=busy**
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1025x52/82e71292be614884fbb23e90b090bf43/image.png)
  
### [20. Crear un contenedor interactivo](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626196#questions)
- Vamos a crear un contenedor un poco más amplio
- Sistema operativo minificado **bare bone** (casi en los huesos :v)
- `docker run -it ubuntu`
  - **error windows mingw64**
    - `the input device is not a TTY.  If you are using mintty, try prefixing the command with 'winpty'`
    - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/772x54/7b7fe562bfea6b798dc4390ad2a551e3/image.png)
    - **mingw64 ok** `winpty docker run -it ubuntu`
    - ![mingw64 ok](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/566x184/902a6736b2a63beb55200673da6049a9/image.png)    
  - **cmder ok**
  - ![cmder ok](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/657x184/a4e967fcbe8401bde66a60d3a2fc1e24/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/709x75/841177a2369669779365bff00d8e32e5/image.png)
- Una imagen en docker está formada por varias capas (con un id)
- Estas capas permiten su reutilización entre varias imágenes
```js
//instala ubuntu mini 
//cmder
docker run -it ubuntu
//mingw64
winpty docker run -it ubuntu

it: inicia sesion con root@<CONTAINER-ID>
```
- Podemos ver el contenedor al que se le agrega un nombre aleatorio
![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1131x69/fbe65504104b206e63cd3edbe85fb453/image.png)
- como se ha instalado un ubuntu minificado puede que no existan todos los comandos
- Lo que consume un contenedor:
![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/658x151/0ef77026605047ad783ad790ae9a51b0/image.png)
- Dos contenedores de una misma imagen
![docker ps](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/984x74/fa706c208b4d310160925f224b3a556a/image.png)
![uname -a](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/1d0433e5ac42155d3e794a48237aef30/image.png)
- contenedor: `cd dev/;ls -l`
  - dispositivos del ubuntu (contenedor), se muestran muy poquitos
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/561x291/e53b10a4deedddb65ca4b5b5b56e7404/image.png)
- contenedor: `exit` salimos del contenedor (se resetean los cambios?, por ejemplo un fichero creado)
  - No, no se resetea
- `dcoker ps -a`:
- ![docker ps -a](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1189x83/a9773c66ffc27e021e3446776b1deb91/image.png)
- Muestra que hemos salido de los contenedores
- **Iniciar sesion en un contenedor:**
  - Esto funciona tanto en **cmder como mingw64**
  - `docker start -i <CONTAINER_ID>`
  - `docker start -i d263e346335d`
- Muy importante: **docker run** crea un nuevo contenedor de una imagen cada vez que se ejecuta
### [21. Prácticas contenedores interactivos](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9691060#questions)
- [5-Contenedores-interactivos.pdf](https://a2.udemycdn.com/2018-03-16_18-37-05-8c262838875e03db98bd45503beb64ff/original.pdf?nva=20191206170809&filename=5-Contenedores-interactivos.pdf&download=True&token=05b228d84abb4a2406bca)
- `docker run -it fedora bash`
- `docker system df` ver lo que ocupan los contenedores
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/743x123/1a584ec62b9bc41a7c92115b8599c2ef/image.png)
- `docker stop` sale del contenedor
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/204x128/1a65c5595f2cba196d40e392037cb4bf/image.png)
### [22. Crear un contenedor en Background](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628330#questions)
- Hemos visto como trabajar con containers interactivos
- En la mayoria de las veces vamos a trabajar con containers en background y pueda interaccionar con el sin la necesidad de una shell
- Para esto vamos a usar un container de **nginx**
- `docker run -d nginx`
- flag -d detached (ejecuta el contenedor como servicio)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/643x169/79f5784510b587093a81464a6912e6b2/image.png)
- Tamaño nginx
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/621x95/015d12f34d09c1dadd650e834ae52e4e/image.png)
- No permite crear sesion interactiva, se queda en espera
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/9604211dc9f1dd6050522cb38f396906/image.png)

### [23. Crear contenedores en Windows](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628524#questions)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/369x374/88b415710e0ba4d272295ecdbb54c25d/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/927x404/0967bc109dea3a53daf7e76ae2d0de3d/image.png)
- Buscando imágenes windows:
  - [Imagenes microsoft en hub.docker](https://hub.docker.com/search?q=microsoft&type=image&certification_status=certified)
- Imagen recomendada por msoft:
  - **microsoft/nanoserver**
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/130bbdef85a90d364fd62073600f6fb5/image.png)
  - Imágen de SO pequeña
  - `docker pull mcr.microsoft.com/windows/nanoserver`
  - A partir de esta imagen básica podemos construir nuestros componentes
  - **microsoft-windows-servercore** una imagen de mayor tamaño.
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/013493628990a06f7e2e739a498f15d7/image.png)
  - `docker pull mcr.microsoft.com/windows/servercore` la imágen es de varios **gigas**
  - Se recomienda esta opción para aquellos que vayamos a trabjar con contenedores windows
- **cmder** `docker version`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/401x314/ee4a02fbc465de889921c465c62849ee/image.png)
- ~~`docker run -it microsoft/nanoserver`~~
  - `Error response from daemon: manifest for microsoft/nanoserver:latest not found: manifest unknown: manifest unknown.`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1003x85/9e9070333c35200bae601330373836f8/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/9f00c21824cb654f1837c0a9e0338c10/image.png)
- Respuesta instructor:
  - > Hola , es que Microsoft ha eliminado elbtag "latest" de sus inagenes. Hay que usar vomo tag el numero de windows que tienes en el pc. En informacion de sistema delnoc aparecec el numero . Debes poner ese tag. Ahora estoy de viaje y no puedovsacar una imagen para que lo veas. En cuanto llegue te mando un ejemplo. Voy a modificar el capitulo para adapyarlo. um saludo
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/575x239/8c2a9fba074257567d9953eb2d6ec666/image.png)
- `docker run -it mcr.microsoft.com/windows/nanoserver:1903`
- `docker pull mcr.microsoft.com/windows/nanoserver:1903`
- docker images:
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/848x56/7c8515a28f1876c383d77f612452b7f3/image.png)
- docker ps -a
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/f16bbb126e2e613b5ad6b832796517f1/image.png)
- docker system df
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/741x100/89ff75a8246b8b295e95415980f85516/image.png)
- sesion en el contenedor:
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/549x377/bb15742f0196882b9ade3c758aecae11/image.png)
### [24. Práctica- Crear contenedores en Windows](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9692684#questions)
- [6-Contenedores en Windows.pdf](https://a2.udemycdn.com/2018-03-17_10-38-17-345f7e5d73eaf6876356d0dbe9317f03/original.pdf?nva=20191206201814&download=True&filename=6-Contenedores-en-Windows.pdf&token=0b2fbcdceebae62db7051)
- saliendo del contenedor:
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1200x145/bfa3d9a38940bcaa5185b470f757b331/image.png)
- usuario:
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/173x49/3bd39406f9e18cdde6816ed9b37c055c/image.png)
### [25. Docker Hub Parte 1: Tags y pulls](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628624#questions)
- Repositiorio de imágenes
- Las imágenes son tanto de particulares como empresas
- Buscamos: **ubuntu**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/494x505/1521c1d61daf19ce9a3ab27ca52ea356/image.png)
- **tags**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/642x97/d6844b11740d222364734ae953af7800/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/682x144/b0c42a5f526e9655cbc4ff0fc1cb5207/image.png)
  - `docker pull ubuntu:trusty`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/783x114/a8b6f380f9a815e5a78ee18747b9c3e7/image.png)
  - Info más detallada de los tags:
    - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/672x363/72e447ccbfc94a451a5e362db73c0b9f/image.png)
- Siempre que se desea recuperar algo del hub hay que ejecutar:
  - `dodcker pull <REPOSITORY>:<TAG>`

### [26. Docker Hub Parte 2: Crear cuenta](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628632#questions)
- La semantica del nombre:
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/702x432/7103757b9fcf4922d32258667f818352/image.png)
- Repos con solo nombre, repositorios root (raiz), pertenecen a empresas de software que tienen acuerdo con docker para que suban sus imágenes.
- Por ejemplo si buscampos python.
- `<usuario>/<nombre-de-la-imagen>` suelen ser imagenes de particulares
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/693x218/363ab518677a93670294bdfc71d3962f/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/185x118/17b37b70f2a8b9dc0251010f519cdf0d/image.png)
- *No puedo crear repositorios desde la docker hub*
- [Más info de como crear un repo desde consola](https://github.com/willitscale/learning-docker/tree/master/tutorial-09)
  - [Learning Docker 09 : Creating a docker repository on Docker hub](https://www.youtube.com/watch?v=EjvNWa_GTK0)
### [27. NOTA IMPORTANTE: Docker Store se integra con Docker Hub](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/14332690#questions)
```
NOTA IMPORTANTE: Docker Store se integra con Docker Hub
Desde Diciembre de 2018, Docker Store se ha unificado con Docker Hub y por lo tanto ha desaparecido. 
Mantengo el vídeo del capítulo siguiente, pero ya no tiene ninguna utilidad, se puede saltar.

Cualquier duda me perseguís por favor.

Un saludo a todos
```
### [28. Docker Store: Diferencias con Docker Hub](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628638#questions)
- Se puede saltar

### [29. Prácticas Docker HUB](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9691070#questions)
- [7-DockerHub.pdf](https://a.udemycdn.com/2018-03-16_18-39-37-a528f264790115fbb68a89792eb56dc9/original.pdf?nva=20191206213003&filename=7-DockerHub.pdf&download=True&token=0b5f3a66c24e8ef12c1cd)
### [30. Borrar imágenes y contenedores](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628642#questions)
- docker rm -f $(docker ps -aq)    select all ids, no solo los activos
- docker rmi -f $(docker images -q)  select ids
### [31. Docker Exec: ejecutar comandos contra contenedores](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628644#questions)
- Crear contenedor con nombre (no con nombre aletorio)
  - `docker run -it --name miubuntu ubuntu bash`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1045x55/cfedbb40540b88b4c80389fb804f7c30/image.png)
- `dcoker exec miubuntu echo hola`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/272x53/b0c52305626dc95f2cc66b9f330d785a/image.png)
  - Esto viene bien para contenedores en modo background
- `docker exec -it miubuntu bash`
- **descargando la imágen**
  - `docker pull python`
  - No instala solo descarga
  - run:
    - baja la imagen      (pull)
    - crea el contenedor
    - arrancar
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/646x261/0aad37f52e6df116d99d48c94bb84cf5/image.png)
  - `docker run -it --name mypython python`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1033x213/f70c7ce93572aa173336a4bb9f404dc2/image.png)
  - `docker exec -it mypython bash`
  - si solo se hace docker -i solo se muestra la panttala negra
  - Una vez que se tiene el contenedor creado no se puede volver a lanzar run con el mismo nombre
    ```
    docker: Error response from daemon: Conflict. The container name "/mypython" is already in use by container 
    "88fa7a2dc5b8d15a72f68879c7545d868166adf68ebab5679457003418a0969f". 
    You have to remove (or rename) that container to be able to reuse that name.    
    ```
  - Si se desea levantar un contenedor se hace con: `docker start mypython`
  - Iniciar sesion en un contenedor que está en ejecución: `docker exec -it mypython bash`
  - El comando **exec** es más para administración de contenedores

### [32. Prácticas: Docker exec y borrados](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9741902#questions)
- [8-docker-Exec-y-docker-rm.pdf](https://a.udemycdn.com/2018-03-21_13-51-33-4b412376e968cf1cd75261f8462d2ea1/original.pdf?nva=20191206235036&download=True&filename=8-docker-Exec-y-docker-rm.pdf&token=0a2d5fafcb45b23e81e42)
- `docker run -d --name nginx1 nginx`
- `docker exec nginx1 date; uname -n`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/303x68/29fcc732ef0aa3269aebb0d8e8504415/image.png)
- **mingw64** `docker exec nginx1 //bin//sh -c 'for archivo in in * ; do echo "fichero_i -->" $archivo ; done'`
- **cmder** `docker exec nginx1 /bin/sh -c "for archivo in in * ; do echo 'fichero_i -->' $archivo ; done"`
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/1b17cef427cb246c3e783a057a0788c9/image.png)
- `winpty docker exec -it nginx1 bash`
- `docker rm nginx1`
- `docker rmi -f fedora` deja un contenedor con imagen fantasma
- ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/22d8afc532c38bf326d4b1ba55551df6/image.png)
- **docker rm `docker ps -aq | grep 9110ae7f579f`** no me ha funcionado
### [33. Comandos Docker Image y Docker container](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628652#questions/8801798)
- La intención es separar comandos de imagen y comandos de contenedores
- `docker image`
  - `docker images` = `docker image ls`
  - `docker rmi` = `docker image rm`
  - Gestiona imágenes
  - `docker image rm ubuntu:ubuntu`
- `docker container`
  - Agrupa todos los comandos que tienen que ver con contenedores
  - `docker ps` = `docker container ls`
    - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1101x71/a023bf8f875810448f608d464cf9f3e4/image.png)
  - `docker container ls --help`
### [34. Docker Logs y Docker Kill](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628656#questions/8801798)
- Hay contenedores que se pueden ejecutar en background
- `docker run -d ubuntu sh -c "while true; do date; done"`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/527x55/12484b390df62dfadb93ee5feb39747f/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1179x72/5c8200bf4653eedaf06106198043c7e6/image.png)
- como está en background no veo lo que está imprimiendo
- con **docker logs** podemos ver lo que esta imprimiendo por pantalla
- esto sirve para ver que es lo que está pasando si por ejemplo un mysql no levanta
- `docker logs 0046eab8d9d1`
  - `docker logs 0046eab8d9d1 --tail  10`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/547x205/cd1d27965c971e2076343b5e9d20c15c/image.png)
- `docker kill <CONTAINER ID>`
  - ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/addf12297da00e5cc032481232e2c1a8/image.png)
  - como se ha eliminado el proceso se guarda con **STATUS** distinto de 0
### [35. Docker Top, Docker Stats](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628658#questions/8801798)
- `docker exec -it ubuntu bash`
- `docker top <CONTAINER ID>|<NAMES>` *nombre exacto*
  - Si tengo la sospecha que un contenedor está consumiendo demasiado puedo visualizar estos procesos
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/559x207/bfeb15fdd5ee10546ba0a115b9ba6111/image.png)
- `docker stats <CONTAINER ID>|<NAMES>` *nombre exacto*
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1182x41/352e7d938a5612fabec238109f46d602/image.png)
- Forzamos uso de cpu y memoria con el siguiente script:
  ```js
  while true; do date; done
  ```
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/408x37/7581ddc0b7fd1e417663b345b14bab40/image.png)  
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1188x56/4688be3345e8b8c340b81b809452899f/image.png)
### [36. Prácticas- Docker logs, stats, top, kill](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9750238#questions/8801798)
- [9-Pr-cticas-Comprobar-estado-de-contenedores.pdf](https://a.udemycdn.com/2018-03-21_23-22-25-1ea15d9f5a377224690d2f630707a89f/original.pdf?nva=20191207183251&filename=9-Pr-cticas-Comprobar-estado-de-contenedores.pdf&download=True&token=06d505c4b6f73331075a6)
- `docker -d --name nginxxx nginx`
  - *importante el que sea --name no va con -n*
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/533x121/bee11edca3eb394ef65f9d2694208e76/image.png)
- `docker exec -it nginxxx bash`
- con el sleep 500
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1179x43/ae5bec2af352048f46e271e06deb0452/image.png)
- `dd if=/dev/zero of=f1.dat bs=1024 count=100000000`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1173x43/987c297e4b388b9b05c8ed42ba5bd1c1/image.png)
- matamos el contendor
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1138x131/1a9297afaebf63166c40177df2f6c38c/image.png)
### [37. Docker inspect](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9628662#questions/8801798)
- Nos permite recuperar información de una img o cont a nivel de sus propiedades, caracteristicas.
- Si deseamos saber la ip, el estado, el path, el hash de la imagen en la que está basado, etc
- `docker inspect <CONTAINER ID>|<NAMES> > dump.json`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/624x45/65e0762f303e5d955ccfd3d66d3471bf/image.png)
- `docker inspect <IMAGE ID>|<REPOSITORY> > dump.json`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/622x43/c1eaebd40e545dcf2d291da132e8f221/image.png)
### []()
- 

## Sección 3: Redes En Docker
- [Github]()
- [Udemy]()

## Sección 4: Volúmenes
- [Github]()
- [Udemy]()

## Sección 5: Crear y gestionar imágenes
- [Github]()
- [Udemy]()

## Sección 6: Docker Compose
- [Github]()
- [Udemy]()

## Sección 7: Docker Registry
- [Github]()
- [Udemy]()

## Sección 8: Docker Swarm. Docker en Cluster
- [Github]()
- [Udemy]()

## Sección 9: Introducción a Kubernetes
- [Github]()
- [Udemy]()

## Sección 10: Otros cursos de Apasoft Training
- [Github]()
- [Udemy]()
