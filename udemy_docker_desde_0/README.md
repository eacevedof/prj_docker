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
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/864x348/530e61d9f38f98bef5337af76d0a3b77/image.png)
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
  - [ejemplo inspect container](https://github.com/eacevedof/prj_docker/blob/master/udemy_docker_desde_0/nginxxx_cfg.json)
- `docker inspect <IMAGE ID>|<REPOSITORY> > dump.json`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/622x43/c1eaebd40e545dcf2d291da132e8f221/image.png)
  - [ejemplo inspect image](https://github.com/eacevedof/prj_docker/blob/master/udemy_docker_desde_0/imgubuntu_cfg.json)
### [38. Práctica. docker inspect](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9753668#questions/8801798)
- ![10-Pr-cticas-inspect.pdf](https://a.udemycdn.com/2018-03-22_07-29-18-5010cbdc74e9b9eea59f57e85b06d84b/original.pdf?nva=20191207190753&filename=10-Pr-cticas-inspect.pdf&download=True&token=0a5a055890d30eb0acdfc)
- `docker pull mongo`
- `docker run -d --name mongoxxx mongo`
- `docker exec -it mongoxxx bash`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/764x210/c65e5090141fca9d5906b19a5d0331c2/image.png)
- `docker exec -it mongoxxx mongo` 
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/782x404/29e7afa6ea61c1328ca13b83b308925c/image.png)
- `docker image inspect mongo | grep MONGO_VERSION`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/422x55/8a0734bf4d9115ae5a31d7ae92ef2308/image.png)
- `docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' mongoxx`
  - las direcciones ip que puede tener el contenedor
- `docker inspect --format='{{.LogPath}}' mongoxxx`
  - donde se deja el fichero log
- `docker inspect --format='{{.Config.Image}}' mongoxxx`
  - la imagen en la que está basado
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/766x174/6045345390c22240373acf13aea5e8f7/image.png)

## Sección 3: Redes En Docker
### [39. Introducción a los puertos en Docker](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9631512#questions/8801798)
- Hasta ahora hemos trabajado con contenedores simples
- Los contenedores deben ser accesibles desde afuera
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/819x421/30961778afe8961b82af19bc5edf6054/image.png)
- La publicación es hostport:vmachineport

### [40. Gestionar Puertos para acceder al contenedor. Ejemplo con NGINX](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630790#questions/8801798)
- El creador de la imagen nos indica como (por que puerto) acceder al servidor
- `docker pull nginx`
- despues de tener la imagen debemos configurar un contenedor al que se pueda acceder
- `docker run -d -P nginx`  **-P** todos los puertos del contenedor se convierten en públicos y la configuración del puerto la gestiona aleatoriamente docker
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1139x51/0bd81485bea01f9a60563edef9ddd99f/image.png)
  - `0.0.0.0` nos indica que vamos a poder acceder desde cualquier ip que tenga la maquina principal
  - Si nuestra pc tuviera dos o más ips (wifi, red, wwan, vpn) podríamos configurar para que solo se acceda de una determinada ip.
  - ` ...0:32768->80/tcp` el puerto local 32768 se traducirá en el puerto 80 del contenedor
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/737x286/41b54d95d38a77a8e058bd05f2b0cfe1/image.png)
- Se crea un puerto aleatorio que empieza desde el 32000
- Mejoramos la conf del puerto (nuevo contenedor): `docker run -d --name nginxx -p 8080:80 nginx`
  - **-p** p minuscula es una conf manual del puerto
  - El puerto 80 de este nuevo contenedor se mapea con el local 8080
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/703x285/1980b0261fd1b8a69a8692bed23c0f6b/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1144x65/6bee1832c2fb71818a3ffdd2a1cb23df/image.png)
### [41. Redes en Docker](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630886#questions/8801798)
- `docker network ls`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/539x88/5f7e5d95a52547f67697f5af8ae2f5d3/image.png)
  - **bridge**: permiten que hayan redes privadas dentro de la maquina y estas se conecten con redes físicas
  - Por defecto siempre hay esa red en docker
  - el **DRIVER** no tiene que ser el mismo que el **NAME**
  - **SCOPE** ámbito si es a nivel local o puede extenderse a otras máquinas (se escapa del alcance del curso)
  - **host**: no se pueden ver entre si, solo con la maquina host
  - **none**: es un contenedor que no tiene nada. Es un proceso
- Todos los contenedores son bridge por defecto
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1135x249/9113fde380c857a4e77b41ef1d6f7a69/image.png)
- La red bridge tiene configurada un rango de ips. La .0.1 es la NIC de enlace, a partir de ahi va asignando.
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1137x224/504cc99b86ec8a6797f6bb88866ab211/image.png)
- comando para inspeccionar la red: `docker inspect nginxy | grep IPAd`
- volcamos el inspect y comprobamos el fichero:
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/663x258/4820e4e887e65602b7109621300d0785/image.png)

### [42. Inspeccionar una red](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630890#questions/8801798)
- `docker network inspect bridge > inspectbridge1.json`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/771x331/9a81211ef6e5074e42917ccfe91787af/image.png)

### [43. Práctica. Trabajar con puertos y redes. Ejemplo con MongoDB](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9753792#questions/8801798)
- [12-Pr-cticas-Puertos-y-Redes.pdf](https://a2.udemycdn.com/2018-03-22_11-13-43-44a0ed16f7cd4641e662cfce896689f8/original.pdf?nva=20191207212013&download=True&filename=12-Pr-cticas-Puertos-y-Redes.pdf&token=01ba7dbeee27af0fedc35)
- comprobar puertos por donde se escucha:
  - `docker inspect --format='{{.Config.ExposedPorts}}' mongo`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/605x307/3d6b019c1004321749e98d273d8ff539/image.png)
```js
$ docker run -d -p 27017:27017 --name mongox mongo
ef6c1a7dd1c590d17f15a144e213e92f58d05d1771fd380d9e411091e4b2af9c
```
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/476x373/647b61a83caa6488bb3474d6ae508990/image.png)
- *no me llega el ping*
- `docker exec -it mongo3 bash`
- `apt-get update`
- `apt-get install iputils-ping -y`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1131x55/a8ea1918d80296ebe57fbca80c5d1d82/image.png)
- `mongo --host 172.17.0.5 --port 27017`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/750x400/49f036f0d8ac4176c20b18a72755c7c5/image.png)

### [44. Crear una nueva red](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630888#questions/8801798)
- Cuando creamos una red: nombre que tiene y el driver al que pertenece
- En la ver más reciente de docker, cuando creamos una red especifica nuestra tipo bridge tiene más caracteristicas que la red bridge por defecto.
- La legacy brige requiere que abramos puertos, la nueva expone todos sus puertos entre ellos.
- `docker network create --help`
```
Options:
  --attachable           Enable manual container attachment
  --aux-address map      Auxiliary IPv4 or IPv6 addresses used by
                          Network driver (default map[])
  --config-from string   The network from which copying the configuration
  --config-only          Create a configuration only network
-d, --driver string        Driver to manage the Network (default "bridge")
  --gateway strings      IPv4 or IPv6 Gateway for the master subnet
  --ingress              Create swarm routing-mesh network
  --internal             Restrict external access to the network
  --ip-range strings     Allocate container ip from a sub-range
  --ipam-driver string   IP Address Management Driver (default "default")
  --ipam-opt map         Set IPAM driver specific options (default map[])
  --ipv6                 Enable IPv6 networking
  --label list           Set metadata on a network
-o, --opt map              Set driver specific options (default map[])
  --scope string         Control the network's scope
  --subnet strings       Subnet in CIDR format that represents a
                          network segment
```
- El **DRIVER** (*flag -d o --driver <string>*) también puede ser overlay que se usará para docker en cluster
- `docker network create red1`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/529x64/c0be98dac4bb5dbd556b2f70bfa19893/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/538x114/eddcefa81d11a56e288666c084e5e538/image.png)
- *he creado una imagen de centos para probar el comando "nmcli con" pero no he tenido éxito :S*
- ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/77189f22965f18d111c8180328287283/image.png)
- `docker inspect red1`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/608x267/b677d913358f4725908971ea0280d6f1/image.png)
- Docker recomienda que creemos nuestras propias redes de modo que cuando asociemos nuestro contenedores a esa red verán todos sus puertos publicados de manera automática.
- `docker network create --subnet=192.168.0.0/16 red2`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/540x63/b7d5496c5659eb6a00ad49996b6cd10f/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/374x187/d100740bc97503661f7517b71c9f5200/image.png)

### [45. Asociar contenedores a una red](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630896#questions/8801798)
- Las redes de tipo bridge se pueden configurar de forma sencilla para que los contenedores que se encuentren en ella puedan conectarse entre si.
- `docker run -it --name <cont NAMES> --network <nw NAME> <REPOSITORY>`
- `docker run -it --name ubuntua --network red1 ubuntu`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/389x91/680c88760770883c97d6fa6a38edf5e4/image.png)
- `docker run -d --name nginx4 --network red1 nginx`
- `docker inspect nginx4 | grep IPAd`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/383x84/196648f6cb7e2feee40c49b4584f54ba/image.png)
- **ping**:*apt-get update; apt-get install iputils-ping -y*
- `ping 172.18.0.3` ok
- **ifconfig**:*apt-get update; apt-get install net-tools -y*
- `apt-get update; apt-get install iputils-ping -y; apt-get update; apt-get install net-tools -y`
- Se puede añadir un contenedor a varias redes. **connect**
- `dcoker network connect <nw NAME> <cont NAMES>`
- `docker network connect red2 ubuntua`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/591x55/8c4b7b73f573f762c67f79039f08ccaa/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/404x165/8d37e0a4f73ef60bff7754e1a38c7f49/image.png)
- `docker network disconnect red2 ubuntua`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/383x135/eea9ed911f2faed05aa4f1fa646cd65f/image.png)

### [46. Prácticas: Creación de redes y asociación de contenedores](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9766566#questions/8801798)
- [13-Pr-cticas-Crear-redes]()
- `docker network ls`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/509x218/48b97edd9a0cc25c0f020e815d79c017/image.png)
- Si estuviera en centos ocurriria esto:
  - Despues de crear la red docker le asigna un id, en mi caso *2af896b355f5*
  - Si inspeccionamos las NIC de centos aparecería un nuevo adaptador levantado y conectado a algo como: br-*2af896b355f5* ...
  - Lo he revisado en windows y solo tengo interfaces que no coincidan con el rango de **net1** que vá de: `172.19.0.1 - 172.19.255.254`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/291x297/2d0fd50b2254db0a5ff0bfd81ebc51fc/image.png)
- `docker run -d -p 27017:27017 --network net1 --name mongo1 mongo`
  - Crear contenedor mongo dentro de la red net1 con un mapeo de puertos fijos
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/378x83/00d889aea8b9e02941f249f1f6504f04/image.png)
- `docker run -d -p 27018:27017 --network net1 --name mongo2 mongo`
  - ping correcto entre mongo1 y mongo2
- `docker network create net2 --subnet=172.30.0.0/16 --ip-range=172.30.10.0/24`
  - subred sea la 172.30.0.0/16
  - Que los contenedores se les asocie una IP que comience a partir de la 172.30.10.0/24
- `docker run -d --name mongo3 --network net2 mongo`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/749x141/92e6b0615b7a5c57c009fc8b7f20734c/image.png)
  ```
  "NetworkID": "b3148cf95d0279b51de5b2dfc6a58b5dd13090f8accfef8516e6e9d4843119c6",
  "EndpointID": "2f6f8cb2ef41ab7ff1979c3f2576e2e776dea021cf6d519e1a3de1a9f965a173",
  "Gateway": "172.30.10.0",
  "IPAddress": "172.30.10.1",  
  ```
  - Si intentamos acceder desde la bash que tenemos abierta en “mongo1” a mongo3 no la encuentra porque no están en la misma subred
- `docker network connect net1 mongo3`
  ```
  "NetworkID": "b3148cf95d0279b51de5b2dfc6a58b5dd13090f8accfef8516e6e9d4843119c6",
  "EndpointID": "2f6f8cb2ef41ab7ff1979c3f2576e2e776dea021cf6d519e1a3de1a9f965a173",
  "Gateway": "172.30.10.0",
  "IPAddress": "172.30.10.1",
  ```
- `ping mongo3`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/587x118/df209f9dcfcfb2aead0b2cbd7025da12/image.png)
- `docker network disconnect net1 mongo3`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/514x88/82a2e84c848461a5f4ca4d66c5c5779f/image.png)

### [47. Enlazar contenedores con --link. Con imagen Busybox](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9631694#questions/8801798)
- Veremos enlaces en bridge por defecto usando flag **--link** 
- Los contenedores que están asociados a la red predefinida
- El flag **--link** se usa para contenedores legacy. Se recomienda no utilizrlo
- Contenedores asociados a otra red esta opción (link) no es necesaria.
- `docker ps -a | wc -l`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/194x57/f8eb5458b78b7f68d597a55bc23e5018/image.png)
- Borrar todos los contenedores 
  ```
  docker rm -f $(docker ps -q)
  ó
  docker rm -f `docker ps -q)`
  ```
- Imagen **busybox**
  - Contenedor navaja suiza. Muy sencillo con utilidades
  - Permite poner aplicaciones encima
  - Tiene utilidades GNU
- `docker run -it --rm --name b1 busybox`
  - Para que no se nos quede en ejecución. En cuanto salgamos borra el contenedor
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/657x142/36270cfa80ac71a288225b6fb32dc153/image.png)
  - `docker exec -it b1 sh`
- Vamos a enlazar un segundo contenedor con este **b1**
- `docker run -it --rm --name b2 busybox`
- `docker run -it --rm --name b3 --link b1:maquina1 busybox`
  - crea un contenedor con el mapeo de b1 en **/etc/hosts**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/420x208/f1d09140fdf876637b397a0eef30cec5/image.png)
- Los enlaces son **unidireccionales** ya que el ping solo lo puede hacer (por nombre) la maquina (contenedor) donde se ha configurado **--link**
### [48. Práctica-Enlazar con link. Ejemplo Drupal y PostgreSQL](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9774582#questions/8801798)
- Enlazar contenedores con `--link`
- Vamos a montar un enlace entre un Drupal (un gestor de contenidos open-source de los más usados) y una Base de datos PosrtgreSQL
- `docker pull drupal`
- `docker pull postgres`
- Vamos en primer lugar a arrancar el contenedor Postgresql y crear la Base de datos. Le tenemos que indicar un nombre y luego una variable de entorno para la password, en este caso he puesto “secret”
- `docker run -d --name pg1 -e POSTGRES_PASSWORD=secret postgres`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1134x69/d61771348314047f53a89ce1730dd1ea/image.png)
  - Podemos ver que la BBDD escucha por el puerto 5432. Como vamos a linkarlo con –link no es necesario “publicar” el puerto, como hemos hecho en el ejercicio anterior.
  - Nos conectamos a la base de datos (la password es la que hemos puesto al crear el contenedor, “secret” en mi caso). Usamos el comando “psql”. Si todo es correcto tenemos base de datos
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/354x81/3e597e5f7bf4e1672c4045bc72d96c9e/image.png)
  - con `\q` salimos de `postgres=#`
- Arrancamos Drupal
- `docker run -d --name dp1 --link pg1:postgres -p 8080:80 drupal`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1150x67/1e7fd4c1b2611c15acb1475fbdb4fbe8/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/712x288/df47349d259e98019b776ea1a564d0ba/image.png)
  - `cat /etc/hosts`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/389x141/ec15b1c6eee7dd817235e340a62485c6/image.png)
  - `pings`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/566x256/bf51602c28695d789a6d5c6f79747c4d/image.png)
- Como ya sabemos link es unidireccional con lo cual no se puede hacer `ping <nombre>` desde postgres a drupal

### [49. Enlazar contenedores en Redes personalizadas. Con imagen Mysql](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9633152#questions/8801798)
- Tenemos dos redes: red1 y red2
- Instalaremos una imagen de mysql
- Cuando se arranca un contenedor crea una bd por defecto 
- Al arrancar el contenedor hay que pasarle una **variable de entorno: -e** **MYSQL_ROOT_PASSWORD**
- Tendremos un mysql **servidor** y uno **cliente**
- `docker run -d --name my_s --rm --network red1 -e MYSQL_ROOT_PASSWORD=secret mysql`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1083x57/184a7e45774d1309d29446c20e20a9d2/image.png)
  - No hemos publicado ningún puerto (-p) porque no queremos acceder desde la maq host sino desde otro contenedor
  - `docker exec -it my_s bash`
  - `mysql -u root -p` nos conectamos al cliente 
- `docker run -it --name my_c --rm --network red1 mysql bash` 
  - importante al final pasar **bash** porque de lo contrario intentará crear la bd
-  en **my_c** `mysql -h my_s -u root -p`
  - conectamos con **my_s**
- No hemos necesitado `--link` ya que al estar los contenedores en una red personalizada, esta (la red), crea su propio DNS de forma que todas las maquinas se ven entre si

### [50. NOTA IMPORTANTE RESPECTO AL SIGUIENTE VÍDEO](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/10714234#questions/8801798)
```
NOTA IMPORTANTE. En la versión 8 de MYSQL han cambiado el tratamiento de las password 
y aplicaciones que no están preparadas no funcionan. por ejemplo wordpress o  joomla.

Por tanto, es necesario descargarse la IMAGEN versión 5.7 o anterior.

También se puede usar MariaDB que es la versión open source de MYSQL
``` 
### [51. Ejemplo enlazar contenedores. WordPress y Mysql](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9633144#questions/8801798)
- Wp se va a conectar a mysql_wp y creara esa bd
- ![arquitectura](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/690x327/1f2354585edc0698ba1c48373a7ba2fa/image.png)
- `docker run -d --name my_wp --rm --network red1 -e MYSQL_ROOT_PASSWORD=secret mysql`
- `docker run -d --name wp -p 8080:80 --rm --network red1 -e WORDPRESS_DB_HOST=my_wp -e WORDPRESS_DB_PASSWORD=secret wordpress`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1068x51/568d638de218eda53e4501bf864cc685/image.png)
- **No está bien** no hemos configurado el puerto (corregido arriba)
- *No conecta con mysql debido al error comentado en 50*
```
[08-Dec-2019 22:29:17 UTC] PHP Warning:  mysqli::__construct(): 
The server requested authentication method unknown to the client [caching_sha2_password]
in Standard input code on line 22

[08-Dec-2019 22:29:17 UTC] PHP Warning:  mysqli::__construct(): (HY000/2054): The server requested 
authentication method unknown to the client in Standard input code on line 22
MySQL Connection Error: (2054) The server requested authentication method unknown to the client
```
### [52. Práctica-Enlazar contenedores con redes personalizadas. Joomla y Mysql](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9778720#questions/8801798)
- 

### [53. Borrar una red](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630898#questions/8801798)
- si hay contenedores en ejecución no deja borrar la red
- `docker network rm red1`
```
λ docker network rm red1
Error response from daemon: error while removing network: network red1 
id ec29947ac692073069cb853e671d91f8e0ba912e286c0b8e201bd123a933405f has active endpoints
```
- `docker stop wp`
- `docker stop my_wp`
- `docker network rm red1`

## Sección 4: Volúmenes
### [54. Conceptos de volúmenes](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630902#questions/8804326)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/748x351/d14501781fa8b94d67a890ae592a06a5/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/655x324/8a21fe05387c383e6325ebc2df3a9777/image.png)

### [55. Crear un volumen en un contenedor](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630904#questions/8804326)
- La forma más facil de crear un volumen es con **-v** al crear el contenedor
```
/var/lib/docker is mounted on the persistent Virtual Disk of the VM which is under C:\Users\Public\Documents\Hyper-V\Virtual hard disks
```


### [56. Visualizar información de volúmenes](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9634186#questions/8804326)
- 
### [57. Práctica: Crear un volumen en contenedor. Imagen Owncloud](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9780654#questions/8804326)
- 
### [58. Crear un directorio compartido con el host](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630908#questions/8804326)
- 
### [59. Compartir volúmenes entre contenedores](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630912#questions/8804326)
- 
### [60. Práctica: Compartir directorios con host principal. Con imagen APACHE HTTPD](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9782042#questions/8804326)
- 
### [61. Crear un volumen independiente](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9634100#questions/8804326)
- 
### [62. Borrar un volumen](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9634094#questions/8804326)
- 
### [63. Practica: Crear volumenes y borrarlos](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9782926#questions/8804326)
- 

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
