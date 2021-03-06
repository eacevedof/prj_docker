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
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/442x135/6583dd430cf253227f655d4014a524f8/image.png)
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
- *tags*:
  - ver rendimiento, comprobar consumo, revisar recursos
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
  docker rm -f `docker ps -q`
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
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/543x96/ec7db4ef2692067789f38833f9c990ec/image.png)
- **docker volume en windows** `docker run --rm -v c:/Users:/data alpine ls /data`
  - Ejemplo real que funciona: `docker run --rm -v e:/docker/dir1:/datos_eaf alpine ls /datos_eaf`
- La forma más facil de crear un volumen es con **-v** al crear el contenedor
```
/var/lib/docker is mounted on the persistent Virtual Disk of the VM which is 
under C:\Users\Public\Documents\Hyper-V\Virtual hard disks
```
- **Si estuvieramos en centos**
  - No deberiamos de tocar este directorio
  - en `/var/lib/docker` encontramos una carpeta **volumes**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/725x168/2e9f3cd186f130cdc0586590cca5881c/image.png)
  - `docker run -it -v /datos_eaf --name ubuntu_v ubuntu bash`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1104x65/684c36ee7e89e643f1a0277e587972f8/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/826x412/a0cc3216186e3afdb17440f0168590f9/image.png)
  - Esto habría creado un nuevo hash dentro de `/var/lib/docker/volumes/<hash-de-datos_eaf>/`
  - Esta ruta es un nuevo directorio con un subdir `_data`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1001x64/a7a0214a93e4a4f0242af71f303d96ed/image.png)
  - A partir de este momento todo el *CRUD* que se realice dentro de `ubuntu_v/datos_eaf` o `centos_host/var/lib/docker/volumes/<hash-de-datos_eaf>/_data/` sera lo mismo ya que es un mapeo de **host_folder:container_folder**
  - Una vez que se crea un contenedor con un volumen ese volumen es persistente.
### [56. Visualizar información de volúmenes](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9634186#questions/8804326)
- Comando `docker volume`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/555x212/2b5a0b2e535d5056b65e77b27d34e838/image.png)
- `docker volume ls`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/684x81/6dfee09147742e29a13a163653fae167/image.png)
- `dcoker volume inspect 2ef303689a893306a0a7dccfbef14fb7f65b90d0038a5b495b12284d51c66fa0`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/713x196/5373314e224718d50810531d792ed123/image.png)

### [57. Práctica: Crear un volumen en contenedor. Imagen Owncloud](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9780654#questions/8804326)
- >ownCloud es una aplicación de software libre del tipo Servicio de alojamiento de archivos, que permite el almacenamiento en línea y aplicaciones en línea (cloud computing). ownCloud puede ser instalado dentro de un servidor que disponga de una versión reciente de PHP (mayor o igual a 5.6) y soporte de SQLite (base de datos por defecto), MySQL o PostgreSQL.
- Volumenes que ya vienen con el contenedor: *OwnCloud*
- Vamos a lanzar un contenedor y vamos a ver como se crea un volumen de forma automática y para ver donde lo deja.
- En este caso vamos a usar una imagen de OwnCloud, que nos permite disponer de nuestro almacenamiento privado en la nube.
- `docker pull owncloud`
- `docker rm $(docker ps -q)`
  - Eliminamos todos los contenedores
- `docker volume prune`
  - Borramos los volumenes huerfanos
- Si comprobamos `centos/var/lib/docker/volumes/` no debería haber nada más que **metadata.db**
- Para probar que funciona correctamente, vamos a crear un contenedor que se elimine al salir
  - `docker run -d --rm -p 80:80 --name cloudx owncloud`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/563x231/5d72d7e691f07ed75630307e9555c257/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1073x352/41a27061dc044551b2d75c2279b61d99/image.png)
- La parte 2 es similar a 56. Me la salto

### [58. Crear un directorio compartido con el host](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630908#questions/8804326)
- La forma ideal de compartir un volumen entre host-contenedor es hacerlo en el arranque
- **NOTA:** Esto no es totalmente compatible con win pq usa el host de centos
- `docker run -it -v /root/dir1:dir1 --name ubuntud2 ubuntu`
- ![](https://trello-attachments.s3.amazonaws.com/5b014dcaf4507eacfc1b4540/5dea358db633626932c2649a/e7e725116a6b63a3c6f50f812354ab8e/image.png)
- `docker run -it -v e:/docker/dir1:/dir1 --name ubuntu2 ubuntu`
  - **error**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/792x99/b4b5b64fa615499fc0b15248ce8e7d25/image.png)
  - **ok**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/509x52/1ddab8ea361a44d1cee44d2e3fdeaebd/image.png)
  - **ok**
- `docker run -v e:/docker/dir1:/dir1 --name ubuntu3 ubuntu`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/470x41/f34c619fe71574ab17c6a938f98afb95/image.png)
- Realmente no es un volumen es un montaje o bind.
- `docker inspect ubuntu2 > ubuntu.json`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/359x118/c8b46adfe64335c61fb89bde298a9d63/image.png)

### [59. Compartir volúmenes entre contenedores](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9630912#questions/8804326)
- Vamos a crear un volumen en un contenedor que sea utilizado por otros contenedores
- `winpty docker run -it -v /datoseaf --name ubuntu4 ubuntu bash`
  - **error** En windows esto crea un directorio **E:** ^^
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/477x84/4836285fd168e6065058ef169eb18944/image.png)
- Pruebo en cmd: `docker run -it -v /datoseaf --name ubuntu4 ubuntu bash`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/512x106/1fc522ce781d2049d7bb4b71a738197f/image.png)
- Ya tenemos el volumen **datoseaf**
- Compartiremos *datoseaf* con ubuntu5 **--volumes-from**
  - `docker run -it --name ubuntu5 --volumes-from ubuntu4 ubuntu bash`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/519x108/1fb380bd3b4c8230f44f5f724732154e/image.png)
- Compartimos **datoseaf** con ubuntu6
  - `docker run -it --name ubuntu6 --volumes-from ubuntu4 ubuntu bash`
- En el momento que borro el último contenedor enlazado a un volumen este queda huerfano y es imposible volverlo a enganchar con un contenedor.
- Los datos se mantienen.
- Para borrar los volumenes huerfanos se usa `docker volume prune`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/528x195/43853d79ebe1000d678b14c7022dc4de/image.png)

### [60. Práctica: Compartir directorios con host principal. Con imagen APACHE HTTPD](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9782042#questions/8804326)
- [17-Practicas-Crear-un-directorio-compartido.pdf]()
- `docker pull httpd` Instlación de APACHE HTTPD
- `docker run -d --name apache1 -p 80:80 --rm -v e:/docker/app:/usr/local/apache2/htdocs/ httpd`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1058x173/0c93fab0c2ef7fef0f7ce919d4d2845d/image.png)
- `docker inspect apache1`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/466x151/b6ec108f7dc37c08688544eaaa740103/image.png)
- compartiremos el directorio `e:/docker/app` con otro contenedor
- `docker run -d --rm --name apache2 -p 8080:80 --volumes-from apache1 httpd`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/983x249/71563ee9af4171f71347ec3cc3d56cef/image.png)

### [61. Crear un volumen independiente](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9634100#questions/8804326)
- `docker volume create vol1`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/480x194/b3839b1914534770aa7e568aa29913b1/image.png)
- con el volumen *vol1* **huerfano** creado vamos a asociarlo a un contenedor
- `docker run -d -it --rm --name ubuntu7 -v vol1:/dir7 ubuntu bash`
- montamos otro contenedor con un dir read-only
- `docker run -d -it --rm --name ubuntu8 -v vol1:/datos_sl:ro ubuntu`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/521x174/5d5ac2b78f909c02a7d35766239cfb07/image.png)

### [62. Borrar un volumen](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9634094#questions/8804326)
- `docker volume rm <VOLUME NAME>`
- antes de borrar un volumen hay que borrar los contenedores que están apuntando a este
- `docker volume prune`

### [63. Practica: Crear volumenes y borrarlos](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9782926#questions/8804326)
- [18-Pr-cticas-Crear-volumenes.pdf](https://github.com/eacevedof/prj_docker/blob/master/udemy_docker_desde_0/practicas/18-Pr-cticas-Crear-volumenes.pdf)

## Sección 5: Crear y gestionar imágenes
### [64. Introducción a las imágenes Docker](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9635216#questions/8804326)
- Capas:
  - bootfs (lectura)
  - rootfs (lectura)
  - n capas de imagen (lectura)
  - container (lectura/escritura)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1136x543/5df527493ab5aee658c13f6eb4b35a79/image.png)
- Cada contenedor es la suma de cada capa de la imágen
- Veremos como modificar un contenedor y crear nuestras propias imágenes
### [65. Modificar un contenedor](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9635050#questions/8804326)
- `docker run -it --name ubuntu1 ubuntu bash` creamos un contenedor
- supongamos que necesito el comando wget
- no lo tengo por defecto
- `apt-get update`
  - Se trae todo lo que necesita, la gestión de los paquetes y el repositorio
- `apt-get install wget -y`
- `wget google.es` ya funciona
- `docker run -it --name ubuntu2 ubuntu bash`
  - no tendría el wget
- Los cambios en un contenedor no se replican a otro
- con `docker diff ubuntu1` o `docker diff <cont NAMES>`
  - A: added, D: deleted, C: changed
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/866x165/1f414ba0324e4f8d651167444d0f43a8/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/183x92/8e855a84724a831675126037a7eafe85/image.png)

### [66. Docker commit. Crear una imagen manualmente](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9635056#questions/8804326)
- Lo mejor es hacer construcción de imagenes automáticas
  - `dcoker commit <cont NAMES> <img REPOSITORY>`
    - Crea imagen a partir de contenedor

- Vamos a usar el cont **ubuntu1**
- `docker commit ubuntu1 mi_ubuntu` el tag por defecto es **latest**
  - Añade la imagen como respositorio 
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1093x210/1a6d7cdd37e96df65bb934c19f221e57/image.png)
- `docker run -it mi_ubuntu bash`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/666x101/f4501161df016f2107ee59a1ef392a1f/image.png)

### [67. Dockerfile](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9635062#questions/8804326)
- Vamos a crear imagenes de forma automática
- Vamos a ver las opciones más importantes de **dockerfile**
- Ejemplo dockerfile:
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/479x244/0dc8dcaaba8756c79400829f6f68de95/image.png)
  - Por cada linea se crea una capa
- dockerfile de ubuntu:
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/836x291/2cb8c12d3bd372af80abe8a6bdbeb41e/image.png)
  - cada directiva es una capa
- [Directivas](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#dockerfile-instructions)

### [68. Crear una imagen de un Dockerfile](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9635066#questions/8804326)
- `docker build -t <img REPOSITORY> <path Dockerfile>`
  - Construye una imágen (repositorio) a partir de un fichero Dockerfile
- `docker build -t imagen_python .`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/925x127/68a6bfb5d1f74b40af6ff37fd38cef34/image.png)
- `docker -it imagen_python python`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/619x124/1a5e09115d4bad4194865b63a19898a8/image.png)

### [69. RUN](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9635082#questions/8804326)
- `docker image history <img REPOSITORY>`
  - Muestra el historico de cambios con los hash de las capas
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/930x317/4b142ee0bd11d978d93e61ab13ca6891/image.png)
- Probamos este Dockerfile
```dockerfile
FROM ubuntu
RUN apt-get update
# no puede haber nada interactivo por eso el flag -y sino daría error
RUN apt-get install -y python
# con && evitamos que se cree una capa por RUN 
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping
```
- `docker build -t imagen_python:v1 .`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/818x210/08da48b2818b0f7d33c572fe2d335ccb/image.png)
- ` docker run -it --rm imagen_python:v1 bash`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/561x236/56f4b0efb5b9d7f6689d8a43a0c2bc00/image.png)

### [70. CMD](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9649772#questions/8804326)
- Nos permite indicar el comando por defecto del contenedor
- Despues de arrancar el contenedor se ejecutará el comando por defecto (el CMD)
```Dockerfile
FROM ubuntu
RUN apt-get update
# no puede haber nada interactivo por eso el flag -y sino daría error
RUN apt-get install -y python
# con && evitamos que se cree una capa por RUN 
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping
# el cmd que vale siempre es el último
CMD echo "Welcome to this container"
```
- `docker build -t image:v1 .`
- `docker run -it --rm image:v1`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/310x48/73ce4a483f9e3032bb49532713690cec/image.png)
```Dockerfile
FROM ubuntu
RUN apt-get update
# no puede haber nada interactivo por eso el flag -y sino daría error
RUN apt-get install -y python
# con && evitamos que se cree una capa por RUN 
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping
# el cmd que vale siempre es el último
# CMD echo "Welcome to this container"
# el comando anterior se ejecuta con /bin/sh -c, ejecuta una shell

# este va en formato json
#CMD ["echo","Welcome to this container"]
# el comando anterior ejecuta como exec

# con este formato se lanzaría: cmd /bin/sh -c  /bin/bash que no es correcto
# lo ideal sería que solo ejecutara /bin/bash es por esto que se monta en un json
# CMD /bin/bash

# con esta directiva hacemos que entre automaticamente en el bash al hacer el run -it
# lo que hay en cmd podría rescribirlo con otro comando (p.e. ls) al lanzar el contenedor
CMD ["/bin/bash"]

# rescritura con: df -h
# docker run -it --rm image:v2 df -h
```
### [71. ENTRYPOINT](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9658432#questions/8804326)
- Al igual que CMD hace algo al arrancar el contenedor
- La diferencia es que ENTRYPOINT obliga a que ese comando se lance siempre
```Dockerfile
FROM ubuntu
RUN apt-get update
RUN apt-get install -y python
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping
# con esta directiva hacemos que entre automaticamente en el bash al hacer el run -it
CMD ["/bin/bash"]
```
- rescribiendo el comando que hay en CMD: `docker run -it --rm image:v2`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/442x146/a52d2dcb91dbc9e4dc360d87e5a70cad/image.png)
```Dockerfile
...
    && apt-get install -y iputils-ping
# la recomendacion es ponerlo en formato json (para su ejecucion con EXEC)
ENTRYPOINT ["/bin/bash"]
```
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/416x60/70a9724289dcaf18dd9ce1b5c1cbfa3a/image.png)
```Dockerfile
...
# diskfile
ENTRYPOINT ["df"]
# solo se tiene en consideración el último ENTRYPOINT
```
- `docker run -it --rm image:v2` lanza: df 
- `docker run -it --rm image:v2 -h` lanza: df -h
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/510x310/7bb3ea2eb530db173963e67349e07f14/image.png)

### [72. WORKDIR](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9671888#questions/8804326)
- Nos permite indicar el directorio de trabajo para otras directivas
- Que un comando se ejecute dentro de un directorio
```Dockerfile
FROM ubuntu
RUN apt-get update
RUN apt-get install -y python
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping
RUN mkdir /datos
WORKDIR /datos
RUN touch f1.txt
RUN mkdir /datos1
WORKDIR /datos1
RUN touch f2.txt
ENTRYPOINT ["/bin/bash"]
```
- `docker build -t image.v3 .`
- `docker run -i --rm image:v3`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/448x78/2757491d4b11f362b2017a7d4c5a76d1/image.png)
### [73. COPY-ADD](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9672634#questions/8804326)
```Dockerfile
FROM ubuntu
RUN apt-get update
RUN apt-get install -y python
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping

## WORKDIR
RUN mkdir /datos
WORKDIR /datos
RUN touch f1.txt
RUN mkdir /datos1
WORKDIR /datos1
RUN touch f2.txt

## COPY
COPY index.html .
COPY app.log /datos

## ENTRYPOINT
ENTRYPOINT ["/bin/bash"]
```
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/751x142/365acb5b1c6d5e9e1823a7996456634f/image.png)
- **ADD**
- ficheros de pruebas
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/142x243/b632e00f3edc58a4c3e9227b69d368d1/image.png)
- **tip**: `tar cvf f.tar f1 f2 f3 f4 f5` **comprimer en f.tar**
```Dockerfile
FROM ubuntu
RUN apt-get update
RUN apt-get install -y python
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping

## WORKDIR
RUN mkdir /datos
WORKDIR /datos
RUN touch f1.txt
RUN mkdir /datos1
WORKDIR /datos1
RUN touch f2.txt

## COPY
COPY index.html .
COPY app.log /datos

## ADD ##
# crea subdir en /datos1/docs y copia ./docs a /datos1/dos
ADD docs docs
# copia todos los f a /datos/
ADD f* /datos/
# esto descomprime f.tar en /datos1
ADD f.tar .

## ENTRYPOINT
ENTRYPOINT ["/bin/bash"]
```
- `docker build -t image:v5 .`
- `docker run -it --rm image:v5`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/380x108/fbf5ef36cbae7caced84ca39c2f0138a/image.png)

### [74. ENV](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9685174#questions/8804326)
- Como usar variables dentro de las imagenes
- Utilizar una var cuando lanzamos un contenedor
- flags: `-e  o --env`
- `docker run -it --rm --env x=10 image:v5`
- `env` devuelve todas las viables de entorno
  - `echo $<nombre variable>`
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/550x398/ed034fdeaad213daf5e7b9cb3687e718/image.png)
```Dockerfile
## ENV
ENV dir=/data dir1=/data1
RUN mkdir $dir && mkdir $dir1

ENTRYPOINT ["/bin/bash"]
```
### [75. ARG](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9691772#questions/8804326)
- Tambien setea variables
- Es similar a ENV
```Dockerfile
## ENV
ENV dir=/data dir1=/data1
RUN mkdir $dir && mkdir $dir1

## ARG
# nos permite pasar variables en la construcción
# no tengo la obligacion de aplicar valor a dir2
ARG dir2
RUN mkdir $dir2

ENTRYPOINT ["/bin/bash"]
```
- `docker build -t image:v6 .`
  - Error falta argumento
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/666x96/6de5f8f3e56c33943cf8e31cedce5614/image.png)
- `docker build -t image:v6 --build-arg dir2=/data_eaf .`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/408x122/cc415760c93bcf84d2160c29745c9bca/image.png)
- `docker build -t image:v7 --build-arg dir2=/data2 --build-arg user=tom .`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/477x114/01af1d2859e96561a2cdf5e2a07af390/image.png)

### [76. EXPOSE](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9691968#questions/8804326)
- Los puertos no se publican por defecto
- Ayuda a la persona que va a utilizar la imagen que puertos va implementar
- creamos un script: entrypoint.sh, arrancará el apache
```sh
# entrypoint.sh
# arrancar apache
echo "arrancando apachectl..."
apachectl start
/bin/bash
echo "apache arrancado!"
```

```Dockerfile
...
## ENV
ENV dir=/data dir1=/data1
RUN mkdir $dir && mkdir $dir1

## ARG
# nos permite pasar variables en la construcción
# no tengo la obligacion de aplicar valor a dir2
# ARG dir2
# RUN mkdir $dir2
# ARG user
# ENV user_docker $user
# RUN /datos1/add_user.sh

## EXPOSE puertos

# instalo apache
RUN apt-get install -y apache2
# publico el puerto 80
EXPOSE 80
# copio mi sh en /datos1
ADD entrypoint.sh /datos1

## CMD
# pq no uso RUN? pq RUN no arranca servicios
# los cambios de estado dentro del cotenedor se hance usando .sh
# si se desea arrancar servicios una vez creado el contenedor
# se debe hacer usando un .sh 
CMD /datos1/entrypoint.sh

# ENTRYPOINT ["/bin/bash"]
```
- `docker run -it --rm image:v7`
- Error con el puerto:
  - > AH00558: apache2: Could not reliably determine the server's fully qualified doma
in name, using 172.17.0.2. Set the 'ServerName' directive globally to suppress t
his message
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/645x66/ceb9186edd76b621ce74336b8e087674/image.png)
  - Hay que mapearlo con la maquina local
- `docker run -it --rm -p 3000:80 image:v7`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1083x54/a567b552ba6fcf9f1b048796af7e1b6d/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/564x203/919c13a2a385250d9c87ef159c631d45/image.png)

### [77. VOLUME](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9707668#questions/8804326)
- Asociar una pagina web a un vol concreto de modo que se pueda compartir entre los distintos contenedores
- carpeta **paginas**
```dockerfile
# Dockerfile
...
## EXPOSE 
RUN apt-get install -y apache2
EXPOSE 80
ADD entrypoint.sh /datos1

# VOLUME
ADD paginas /var/www/html
# similar a -v
VOLUME ["/var/www/html"]

# arranca apache
CMD /datos1/entrypoint.sh

# ENTRYPOINT ["/bin/bash"]
```
- `docker build -t image:v8 .`
- `docker run -it --rm --name ap1 -p 3000:80 image:v8`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1077x51/0f0c480fa8dd577ade894c1adcef3ec0/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/591x271/73fd368c11db37379ed1e3c7e484e361/image.png)
- `docker volume inspect <hash>`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/964x188/300c57d201a0ea9905d3b73053a34f29/image.png)
- **--volumes-from**
- `docker run -it --rm -p 9000:80 --volumes-from ap1 --name ap2 image:v8`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/600x146/bf844861cfe0401fdf1d32c8c0a6e157/image.png)
  - no se ha creado otro volumen

### [78. Práctica Dockerfile 1: Crear una imagen de Nginx](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9797880#questions/8804326)
- To-Do:
  - Vamos a realizar un ejemplo práctico de Dockerfile  creando una imagen de Nginx con variables de entorno, ficheros asociados.y volúmenes
- *solo hago la última práctica* **counter-strike**
  ```Dockerfile
  FROM ubuntu:12.04
  MAINTAINER Apasoft Formacion "apasoft.formacion@gmail.com"
  RUN apt-get update
  RUN apt-get install -y nginx
  ##RUN echo 'Mi primer Dockerfile' > /usr/share/nginx/www/index.html
  VOLUME /usr/share/nginx/www/
  ARG webpage
  ADD $webpage /usr/share/nginx/www/
  ENTRYPOINT ["/usr/sbin/nginx", "-g", "daemon off;"]
  EXPOSE 80  
  ```
  - **construimos la imagen**
  - `docker build -t trainingdock/nginx:v3 --build-arg webpage=web1`
  - **creamos el contenedor**
  - `docker run -d -p 80:80 --name nginx2 --rm trainingdock/nginx:v3`
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/1107x77/53ffceff3056d52343b628f1885a0e68/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/792x226/f1144f24c030fb41034cab970c098a29/image.png)

### [79. Práctica Dockerfile 2. Crear imagen PostgreSQL con variables y scripts](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9858260#questions/8804326)
- > En esta práctica puedes probar la construcción de una imagen de la Base de Datos PostgreSQL con variables y scrtips
- *me salto la práctica*
```Dockerfile
# dockerfile
##Si seleccionamos otra versión de Ubuntu, puede que
##tengamos que modificar el fichero para adaptarlo
FROM ubuntu:14.04
MAINTAINER Apasoft Training <aapasoft.training@gmail.com>
## Añadimos la clave PGP de PostgreSQL para verificación.
## Debería coincidir con
## https://www.postgresql.org/media/keys/ACCC4CF8.asc
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8
##Añadimos el respositorio de PostgreSQL's repository.
## Llamamos a la 9,3. Si cambiamos de version es posible
##que tengamos que modificar el Dockerfile
RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ precise-pgdg main" > /etc/apt/sources.list.d/pgdg.list
##Actualizamos los repositorios de Ubuntu PostgreSQL ## ##Debemos instalar python-software-properties
###software-properties-common y PostgreSQL 9.3
RUN apt-get update && apt-get -y -q install python-software-properties software-properties-common \
&& apt-get -y -q install postgresql-9.3 postgresql-client-9.3 postgresql-contrib-9.3

##Nos cambiamos al usuario postgres, que se ha creado
##al instalar postgreSQL
USER postgres
##Creamos un usuario denominado “pguser” con password
##”secret” y creamos una base de datos llamada “pgdb”
RUN /etc/init.d/postgresql start \
&& psql --command "CREATE USER pguser WITH SUPERUSER PASSWORD 'secret';" \
&& createdb -O pguser pgdb
##Nos cambiamos a usuario ROOT
USER root
##Permitimos que se puede acceder a PostgreSQL
##desde clientes remotos
RUN echo "host all all 0.0.0.0/0 md5" >> /etc/postgresql/9.3/main/pg_hba.conf
##PErmitimos que se pueda acceder por cualquier
##IP que tenga el contenedor
RUN echo "listen_addresses='*'" >> /etc/postgresql/9.3/main/postgresql.conf
##Exponemos el Puerto de la Base de Datos
EXPOSE 5432
##Creamos un directorio en /var/run y le damos permisos
##para el usuario postgres
RUN mkdir -p /var/run/postgresql && chown -R postgres /var/run/postgresql
##Creamos los volúmenes necesarios para guardar
##el backup de la configuración, logs y bases de datos
##y poder acceder desde fuera del contenedor
VOLUME ["/etc/postgresql", "/var/log/postgresql", "/var/lib/postgresql"]
##Nos cambiamos al usuario postgres
USER postgres
##Indicamos el comando a ejecutar al crear el contenedor
##Básicamente arrancar posrtgres con la configuración
##adecuada
CMD ["/usr/lib/postgresql/9.3/bin/postgres", "-D", "/var/lib/postgresql/9.3/main", "-c", "config_file=/etc/postgresql/9.3/main/postgresql.conf"]
```
- `docker build -t trainingdock/postgtres:v1 .`
- `docker run -d --name postgres1 --network net1 trainingdock/postgres:v1`
- `docker run -it --name postgres2 --rm --network net1 trainingdock/postgres:v1 bash`
```sh
# entrypoint.sh
##Arrancamos la Base de Datos para el procedimiento
inicial
/etc/init.d/postgresql start
##Creamos el usuario, la pass y la Base de datos
psql --command "CREATE USER ${USER} WITH SUPERUSER
PASSWORD '${PASS}';"
createdb -O pguser ${BBDD}
##PAramos la instancia
/etc/init.d/postgresql stop
##Arrancamos de forma normal
exec /usr/lib/postgresql/9.3/bin/postgres -D
/var/lib/postgresql/9.3/main -c
config_file=/etc/postgresql/9.3/main/postgresql.conf
##Si seleccionamos otra versión de Ubuntu, puede que
##tengamos que modificar el fichero para adaptarlo
FROM ubuntu:14.04
MAINTAINER Apasoft Training <apasoft.training@gmail.com>
## Añadimos la clave PGP de PostgreSQL para verificación.
## Debería coincidir con
## https://www.postgresql.org/media/keys/ACCC4CF8.asc
RUN apt-key adv --keyserver keyserver.ubuntu.com --recvkeys
B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8
##Añadimos el respositorio de PostgreSQL's repository.
## Llamamos a la 9,3. Si cambiamos de version es posible
##que tengamos que modificar el Dockerfile
RUN echo "deb http://apt.postgresql.org/pub/repos/apt/
precise-pgdg main" > /etc/apt/sources.list.d/pgdg.list
##Actualizamos los repositories de Ubuntu PostgreSQL ##
##Debemos instalar python-software-properties
###software-properties-common y PostgreSQL 9.3
RUN apt-get update && apt-get -y -q install pythonsoftware-
properties software-properties-common \
&& apt-get -y -q install postgresql-9.3 postgresqlclient-
9.3 postgresql-contrib-9.3
##Nos cambiamos a usuario ROOT
USER root
##Permitimos que se puede acceder a PostgreSQL
##desde clientes remotos
RUN echo "host all all 0.0.0.0/0 md5" >>
/etc/postgresql/9.3/main/pg_hba.conf
##PErmitimos que se pueda acceder por cualquier
##IP que tenga el contenedor
RUN echo "listen_addresses='*'" >>
/etc/postgresql/9.3/main/postgresql.conf
##Exponemos el Puerto de la Base de Datos
EXPOSE 5432
##Creamos un directorio en /var/run y le damos permisos
##para el usuario postgres
RUN mkdir -p /var/run/postgresql && chown -R postgres
/var/run/postgresql
##Creamos los volúmenes necesarios para guardar
##el backup de la configuración, logs y bases de datos
##y poder acceder desde fuera del contenedor
VOLUME ["/etc/postgresql", "/var/log/postgresql",
"/var/lib/postgresql"]
##Copiamos el fichero entrypoint.sh y le ponemos permisos
ADD entrypoint.sh /usr/local/bin
RUN chmod +x /usr/local/bin/entrypoint.sh
##Nos cambiamos al usuario postgres
USER postgres
##Creamos 3 variables para crear el usuario,
##la password y la base de datos
ENV PASS=secret
ENV BBDD=pgdb
ENV USER=pguser
##Ejecutamos el script entrypoint.sh
CMD /usr/local/bin/entrypoint.sh
```
- `docker build -t trainingdock/postgres:v2 .`
- `docker run -d --name postgres2 --network net1 -e PASS=password -e BBDD=bd1 -e USER=pguser trainingdock/postgres:v2`
- `docker exec -it postgres2 bash`

### [80. Repaso de Docker Hub](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9705848#questions/8804326)
- Subir nuestras imágenes al repo de docker hub
- Dockerhub solo permite una cuenta privada gratuita
- nombres tipo raiz "fabricantes"
- nombre-usuario/repositorio "particulares"
  - mi caso: **ioedu/<repositorio>**
- vamos a ver como subir alguna de las img que hemos ido creando

### [81. Subir imágenes a Docker Hub](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9706114#questions/8804326)
- [Crear repo](https://hub.docker.com/repository/create)
- Conectar con dockerhub
  - `docker login`
- directamente con docker push no podría subirlo por no respetar el patron **`<mi-usuario>/<img-nombre>:<tag>`**
- debo cambiar a un nombre valido la imagen (con docker image tag)
- **`docker image tag image:v7 ioedu/testimg:v7`**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/697x115/bb09b95e6d8c6ce5137c85f71950d1ee/image.png)
- **`docker push ioedu/testimg:v7`**
  - ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/475x95/aba741ff7da59563d9491fcf831f7684/image.png)
- Cuando hemos renombrado la imagen le hemos pasado v7 como tag, pero podriamos haber puesto **latest**
  - `docker image tag image:v7 ioedu/testimg:latest`
- Una vez que está subido podemos agregar información por tag.
- *me está tardando mucho el push ^^ como 15min y sigue...*
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/790x144/6552ccfd593d7ba4c01b538de5af4319/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dea358db633626932c2649a/970x87/3ba9c16e98a3e5094dd8a95bf0bea0a7/image.png)
- `docker pull ioedu/testimg:v7`

### [82. Integración continua. Ejemplo: Conectar DockerHub y GIthub de forma automática](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9707152#questions/8804326)
- Cada vez que se actualice en **github** automaticamente se creará una imagen asociada en **docker hub**
- Creamos el repo [**prj_docker_ci**](https://github.com/eacevedof/prj_docker_ci)
- Copiamos `sec5\imagen_python` en este repo
- Vinculamos cuentas:
  - [linked-accounts](https://hub.docker.com/settings/linked-accounts)
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/557x360/6694f4a70acf4b4254becac27c4e1435/image.png)
  ```sh
  # email
  Hey eacevedof!
  A third-party OAuth application (Docker Hub Builder) with repo scope was recently authorized to access your account.
  Visit https://github.com/settings/connections/applications/<token> for more information.
  To see this and other security events for your account, visit 
    https://github.com/settings/security
  If you run into problems, please contact support by visiting 
    https://github.com/contact
  Thanks,
  The GitHub Team
  ```
  - Configuro el repo en docker hub:
    - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/992x251/161f45b81c7ea41317b2b03be6bffffc/image.png)
    - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/919x291/12f904e5c13be0208e1e788802be9ddf/image.png)
    ```sh
    # email
    The following SSH key was added to the eacevedof/prj_docker_ci repository by eacevedof:
    Docker Cloud Build
    xx:yy:zz:...
    If you believe this key was added in error, you can remove the key and disable
    access at the following location:    
    ```
- Con cada push en **github** se lanzará un autobuild en docker hub
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/907x130/939470ec8e0c8b194b9266c0cf35f4fa/image.png)
  - Al tener la cuenta gratuita la encola
- Esto nos permite que con cada cambio en una app se actualice su imagen
### [83. Práctica: Subir imágenes a DockerHub](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9860878#questions/8804326)
- El ejemplo trata sobre la subida de las imagenes de la práctica anterior

## Sección 6: Docker Compose
### [84. Introducción a Docker Compose](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9692498#questions)
- El potencial de docker es poder enteneder los contenedores como microservicios
- Yo podría configurar una arquitectura de microservicios pero hacerlo de forma manual es muy laborioso
- Docker Compose orquesta estos servicios
- Contiene las instrucciones que relacionan estos contenedores
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/922x359/c369037b60aa35d2715e82fa624ddd59/image.png)
- Ejemplo **stack MEAN**:
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1098x490/725fc4041345ad48771a02173cb0a14c/image.png)

### [85. Instalar Docker Compose](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9696910#questions)
- En windows ya viene el instalador de docker-compose
- En linux hay que usar curl de un repo de github
- comando: **docker-compose**
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/684x334/2fe2494e96ba06cb15983adc8047fd99/image.png)

### [86. Fichero docker-compose.yml](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9698422#questions)
- **docker-compose.yml**
- Fichero escrito en YAML - Yet another markup language
- Usaremos un lenguaje ya predefinido
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/374x57/61d4d0c83827e5fda9d242e6a9da9b90/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/451x326/e675de8b7b70c689b2eccebba13fce95/image.png)
```yaml
version: "3"
services: 
  web:
    # construye la imagen con dockerfile
    build: .
    ports:
    - "5000:5000"
    volumes: 
    - .:/code
    - logvolume01:/var/log
    links: 
    - redis
  redis:
    image: redis

volumes:
  logovolume01: {}
```
- En **services** tendremos todos los servicios y ponemos nombres descriptivos
- Cada servicio es un contenedor
- Todo servicio debe tener o el comando **build** o **image**

### [87. Mi primer proyecto Compose](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9698434#questions)
- crear carpeta **pr_nginx**
```yml
version:  "3"
services: 
  minginx:
    image: nginx
    ports:
    - "80:80"
```
- dentro de la carpeta **pr_nginx** ...
- `docker-compose up`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/625x83/878fe65ffb5c2d034bcc0f69ef10bb48/image.png)
  - Se queda en modo servicio 
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1175x77/c37e339c1b49c06bf79c617d94092fd9/image.png)
- Con el contenedor levantado podría trabajar con el comando **docker** pero no es recomendable.
- Ha creado una red:
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/548x135/a68a0c4c68c840092e0fa571f6ed36f1/image.png)
- **`docker-compose ps`**
  - muestra el conjuto de microservicios
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/620x98/998a46a7e1f0e2019caca3927dfbd62d/image.png)
- En **docker-compose** hay comandos similares a **docker**
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/619x415/660884c2aa9165b6e0e21e2055591f63/image.png)
- Si detengo docker-compose (ctrl+c)
- Si lo tendría ejecutandose en modo background para detener docker-compose hubiera tenido que uasar **docker-compose stop**

### [88. Práctica: Crear un Docker Compose básico](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9861416#questions)
- Ejemplo se basa en la imagen nginx:v3 (counterstrike)
- Me salto la práctica, no tengo nginx:v3

### [89. Enlazar servicios. Puertos y variables](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9863402#questions)
- Ejemplo: wordpress y mysql
- wp acceso: u:y pass: (e)tmt(v)
```yml
# docker-compose.yml cap_88
version: "3"

services: 
  # mi php
  wordpress:
    image: wordpress
    environment: 
      # apunta a otro servicio
      WORDPRESS_DB_HOST: dbserver:3306
      WORDPRESS_DB_PASSWORD: mysqlpw
    # es lo mismo que -p
    ports:
      - 80:80
    # para q wp funcione antes tiene que arrancar dbserver
    depends_on: 
      - dbserver

  # mi bd
  dbserver:
    image: mysql:5.7
    environment: 
      MYSQL_ROOT_PASSWORD: mysqlpw
    ports:
      - 3306:3306
```
- `docker stats`
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1181x62/b2b88be832847d6e70cd790e533fc191/image.png)
```
λ docker network ls
NETWORK ID          NAME                DRIVER              SCOPE
f260be727fac        bridge              bridge              local
a526dce0e0d0        cap_89_default      bridge              local
ef5418a416d9        host                host                local
```
### [90. Diversos comandos de Docker-Compose](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9863672#questions)
- Veremos algunos de los comandos
- `docker-compose ps` ya visto
- `docker-compose images`
  - con docker images no veria este contenido
- `docker-compose config`
  - Muestra el contenido de docker-compose.yml
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/447x305/6744a290f7e68b72c4f13e367ecfa90a/image.png)
  - flag `-q` comprueba si hay algun error
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/594x100/7384bb20769aa872cb9a3532729ab7ff/image.png)
- `docker-compose start`
  - Arranca los servicios
- `docker-compose logs wordpress`
- `docker-compose top dbserver`
```
λ docker-compose top dbserver
cap_89_dbserver_1
El sistema no puede encontrar la ruta especificada.
PID    USER   TIME   COMMAND
----------------------------
5555   999    0:03   mysqld
```
- `docker-compose pause`
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/785x200/3110fdf89f2ff62fd26d25ea7ad8a31e/image.png)
- `docker-compose unpause`
- `docker-compose restart`
- `docker-compose rm`
  ```
  λ docker-compose rm
  Going to remove cap_89_wordpress_1, cap_89_dbserver_1
  Are you sure? [yN] y
  Removing cap_89_wordpress_1 ... done
  Removing cap_89_dbserver_1  ... done  
  ```

### [91. Volúmenes en Docker Compose](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9872356#questions)
- carpeta: sec6/cap_91
- recurso: docker-compose.yml
```yml
version: "3.2"
services:
  web:
    image: nginx:alpine
    volumes:
      # tipo volume crea un hash en la maq virtual
      - type: volume
        source: mydata
        target: /data
        volume:
          nocopy: true
      
      # bind: mapeo de directorios maq host y contenedor
      - type: bind
        source: ./static
        target: /opt/app/static
    ports:
      - 80:80
  db:
    image: postgres:latest
    volumes:
      # bind: mapeo de ficheros maq host y contenedor
      - "/var/run/postgres/postgres.sock:/var/run/postgres/postgres.sock"
      - "dbdata:/var/lib/postgresql/data"

volumes:
  # redeclaramos estos vol q tenemos como tipos volume y no como bind
  # para confirmar que son volumenes
  mydata:
  dbdata:
```
- Evidentemente a mi en windows esto no me va a funcionar el socket
- creo fichero static/f1
- `docker-compose exec web sh`
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/605x348/6d3192edc8e899ba97dede288d039992/image.png)
- `docker-compose down`
  - para los servicios
  - borra los volumenes
  - borra los contenedores
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/612x119/1519e09bc285d3f44818deee81de6f07/image.png)
- `docker volume prune`

### [92. Redes en Docker Compose](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9872366#questions)
- Usando recursos del capitulo en cap_92
- Despliegue de app en node.js y mongo
- En este cap se presta atención a la configuración de redes
- **Dockerfile**
  ```Dockerfile
  # recupera imagen de node
  FROM node:8.4
  # copia todo lo que hay en cap_92 dentro de <contenedor>/app
  COPY . /app
  # hace un cd dentro de <contenedor>/app
  WORKDIR /app
  # ejecuta npm e install
  RUN ["npm", "install"]
  # publica el puerto 3000
  EXPOSE 3000/tcp
  # lanza el servicio
  CMD ["npm", "start"]
  ```
- **docker-compose.yml**
  ```yml
  version: '3.3'

  services:
    app:
      image: client
      # le puedo dar un nombre al contenedor
      container_name: client
      # construye la imagen a partir de Dockerfile
      build: .
      ports: 
        - 80:3000
      environment:
        # apunta al contenedor del servicio db "mongo_db"
        - MONGO_URI=mongodb://mongo_db/sample
      depends_on: 
        - db

      # ejecuta: --network net3
      networks: 
        - net3
    
    db:
      image: mongo:3.0.15
      container_name: mongo_db
      volumes:
        # esto parece que da un error
        - /db:/data/db
      networks:
        # como se va a configurar más cosas en net3 no se usa -
        net3:  
          aliases:
            - "mongo_db"     # un alias
            # otro nombre alternativo por si hay otro servicio apuntando a ese nombre
            - "mongo_server" 
          ipv4_address: 172.16.238.10
          ipv6_address: 2001:3984:3989::10

  networks:
    # crea red: cap_92_net3
    net3:
      driver: bridge
      ipam:
        driver: default
        config:
        -
          subnet: 172.16.238.0/24
        -
          subnet: 2001:3984:3989::/64
  ```
- *dentro de cap_92* `docker-compose up`
  - **error**
  ```
  # da error al levantar mongo, me crea la carpeta db pero como que no puede escribir
  # he configurado todos los permisos y no consigo que escriba
  # en google no hay mucha info
  3b235ec82f1c_mongo_db | 2019-12-21T14:02:29.124+0000 I JOURNAL  [initandlisten] journal 
  dir=/data/db/journal
  3b235ec82f1c_mongo_db | 2019-12-21T14:02:29.126+0000 I JOURNAL  [initandlisten] recover : 
  no journal files present, no recovery needed
  3b235ec82f1c_mongo_db | 2019-12-21T14:02:29.129+0000 I JOURNAL  [initandlisten] info 
  preallocateIsFaster couldn't run due to: couldn't open file 
  /data/db/journal/tempLatencyTest for writing errno:9 Bad file descriptor; returning false
  3b235ec82f1c_mongo_db | 2019-12-21T14:02:29.132+0000 I STORAGE  [initandlisten] exception 
  in initAndListen: 13516 couldn't open file /data/db/journal/j._0 for writing errno:9 
  Bad file descriptor, terminating

  # por el error anterior el cliente da error
  Please check that you have mongo installed or an environment variable "MONGO_URI" 
  with a URL pointing to a running Mongo server.     

  /app/node_modules/mongodb/lib/server.js:267
    process.nextTick(function() { throw err; })
                                      ^       
  MongoError: failed to connect to server [mongo_db:27017] on first connect 
  [MongoError: getaddrinfo ENOTFOUND mongo_db mongo_db:27017]
    at Pool.<anonymous> (/app/node_modules/mongodb-core/lib/topologies/server.js:328:35)
  ```
  - ~~**sol**~~
  - ~~Habia que ejecutarlo con `docker-compose up -d`~~

### [93. Práctica: crear un MEAN Stack con Composer](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9874566#questions)
- [22-Pr-ctica-Docker-Compose-mean-stack]()
- Instalamos Angular-cli `npm install -g @angular/cli`
- `mkdir mean`
- `ng new angular-cli` crea carpeta angular-cli
- `ng serve` sirve el sitio por 4200
- `Paramos el servidor con CTRL-C`
- En package.json
  - `"start": "ng serve --host 0.0.0.0",`
- Dentro de la carpeta **angular-cli** creamos el dockerfile
```Dockerfile
# Lo iniciamos con la imagen official de Node 8
FROM node:latest
# Vamos a crear un directorio donde dejar la aplicación Angular
RUN mkdir -p /usr/mi-app
# Nos cambiamos a ese directorio
WORKDIR /usr/mi-app
# Copiamos el paquete json para gestionar las dependencias
COPY package.json /usr/mi-app
# Instalamos esas depndencias
RUN npm install
# Copiamos el código que hemos generado en el punto anterior, al crear la aplicación angular-cli
COPY . /usr/mi-app
# Exponemos el Puerto
EXPOSE 4200
# Arrancamos
CMD ["npm", "start"]
```
- dentro de **angular-cli**
- crear imagen: `docker build -t angular-cli:v1 .`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/710x95/21e47deaf67842453118006111d7f996/image.png)
- crear el contenedor: `docker run -d --name a1 -p 4200:4200 angular-cli:v1`
- **servidor express**
- `npm install express-generator -g`
- `express myapp`
- `cd myapp`
- `npm install`
```Dockerfile
# Lo iniciamos con la imagen oficial de Node 8
FROM node:latest
# Vamos a crear un directorio donde dejar la aplicación Angular
RUN mkdir -p /usr/mi-app
# Nos cambiamos a ese directorio
WORKDIR /usr/mi-app
# Copiamos el paquete json para gestionar las dependencias
COPY package.json /usr/mi-app
# Instalamos esas depndencias
RUN npm install
# Copiamos el código que hemos generado en el punto anterior, al crear la aplicación express
COPY . /usr/mi-app
# Exponemos el Puerto
EXPOSE 3000
# Arrancamos
CMD ["npm", "start"]
```
- `docker build -t server:v1 .`
- `docker run -d --name e1 -p 3000:3000 server:v1`
- **5. Conectar los componentes . Docker Compose**
- creamos dentro de mean el fichero: **docker-compose.yml**
```yml
# Vamos a definir los servicios y contenedores a usar
version: '3'

services:
  # Preparamos el cliente
  angular:
    image: angular-cli:v1 # 
    ports:
     - "4200:4200" # Puerto del cliente
  
  # Preparamos el servidor
  servidor:
    image: server:v1
    ports:
     - "3000:3000" #Puerto del servidor

  #Contenedor de Mongo
  database:
    image: mongo
    ports:
     - "27017:27017"
```
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/669x260/2fcf87d05eb4e7a9bd913c7a3fbe08f4/image.png)

### [94. Algunas opciones interesantes en Dockerfile](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9876792#questions)
- docker-compose opciones útiles:
  ```ssh
  Options:
  -f, --file FILE          Specify an alternate compose file (default: docker-compose.yml)
  -p, --project-name NAME  Specify an alternate project name (default: directory name)
  ```
- **-f** | **--file FILE**
  - `docker-compose -f any-file-name.yml`
  - Que el fichero no se tenga que llamar docker-compose.yml
- **-p** | **--project-name <NAME>** 
  - `docker-compose --project-name this-prj-name`
  - Por defecto el nombre del proyecto equivale al nombre del directorio
- creamos `compose-wp-mysql.yml` *copia de cap_89/docker-compose.yml*
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/596x123/e68c45d7a0197a8b95bc7173f9a7c730/image.png)
- `docker-compose -f compose-wp-mysql.yml -p pr1 up -d` *-d ejecuta en background*
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/773x156/938ecff87f0d1edc9cf4b22d51ab7e7d/image.png)
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/639x72/1db45b4e8ba59674b707b306df764d06/image.png)
- `docker-compose ps` no mostrará nada, porque busca el proyecto con el nombre del directorio
- `docker-compose -p pr1 ps` le indicamos el nombre del proyecto
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/759x227/e9fae58505abfadc070981e09013397b/image.png)
```sh
λ docker-compose -p pr1 ps                                                                   
El sistema no puede encontrar la ruta especificada.                                          
     Name                    Command               State                 Ports               
-------------------------------------------------------------------------------------------- 
pr1_dbserver_1    docker-entrypoint.sh mysqld      Up      0.0.0.0:3306->3306/tcp, 33060/tcp 
pr1_wordpress_1   docker-entrypoint.sh apach ...   Up      0.0.0.0:80->80/tcp                
```

## Sección 7: Docker Registry
### [95. Introducción a Docker Registry](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/11582990#questions)
- Docker Registry es como un docker hub privado
![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1022x477/541719b54630b8476c27466ec8513cf6/image.png)

### [96. Crear un registro de imágenes](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/11583588#questions)
- Hay que crear un contenedor basado en la imágen registry
- Podemos tener tantos registros como contenedores podamos crear
- Estos contenedores se almacenan en un volumen
- Ahí se alojarían todas las imágenes
- `docker pull registry`
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/645x197/b92ef9cd62383f21b5175acd7765b1f3/image.png)
- `docker run -d -p 5000:5000 --name reg1 registry`
  - se suele usar por convenio el puerto 5000
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1181x140/1a4c5cc01f21542c9cbaa8e96d31bb3e/image.png)
- Los nombres podrían ser las clasificaciones por departamentos en una empresa.
- Puedo tener más de un registro pero no se puede usar el mismo puerto
- `docker run -d -p 5001:5001 --name reg2 registry`
- En este punto ya tengo dos registros **reg1 y reg2** con lo cual ya puedo subir unas imagenes a uno y otras a otro
- Es un tema de organización. No es obligatorio crear un registro por grupo de imágenes

### [97. Subir y bajar imágenes del registro](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/11659550#questions)
- Vamos a asociar nuestra imagen de ubuntu a nuestro registro uno **reg1**
- Antes de subir cualquier imagen a un registro hay que etiquetarla.
- Para etiquetar:
  - `docker image tag <img-original> <un-repo-name>/<img-nombre>:<tag>`
  - Como ya cuento con una imagen de ubuntu:latest lo hago con esta
  - `docker tag ubuntu localhost:5000/miubu`
```sh
λ docker images localhost:5000/miubu
REPOSITORY             TAG                 IMAGE ID            CREATED             SIZE
localhost:5000/miubu   latest              775349758637        7 weeks ago         64.2MB
```
- Subir la imágen:
  - `docker push localhost:5000/miubu`
  ```
  λ docker push localhost:5000/miubu
  The push refers to repository [localhost:5000/miubu]
  e0b3afb09dc3: Pushed
  6c01b5a53aac: Pushed
  2c6ac8e5063e: Pushed
  cc967c529ced: Pushed
  latest: digest: sha256:some-hash size: 1152  
  ```
- En la vida real debería subirlo a un servidor de la organización
- Descargar la imágen:
  - comprobar todo lo que hay en el registro:
  - Todas las imagenes locales 
  ```
  λ docker images localhost:5000/*
  REPOSITORY             TAG                 IMAGE ID            CREATED             SIZE
  localhost:5000/miubu   latest              775349758637        7 weeks ago         64.2MB
  ```
  - Borrando a nivel local
  - `docker rmi localhost:5000/miubu`
  - descargando...: `docker pull localhost:5000/miubu`

### [98. Cambiar el almacenamiento del Docker Registry](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/11660588#questions)
- Comprobar y modificar el sitio donde tenemos el registro
- Lo ideal es tener el registro en una unidad de disco que sea rápida
- Hay que usar la opción -v para modificar el sitio donde almacenaremos las imágenes
- creo carpeta reg_docker
```
E:\projects\prj_docker\udemy_docker_desde_0\sec7\cap98\reg_docker (master -> origin)
λ docker run -d --name cont1 -p 5000:5000 -v 
E:\projects\prj_docker\udemy_docker_desde_0\sec7\cap98\reg_docker:/var/lib/registry registry
Unable to find image 'registry:latest' locally
latest: Pulling from library/registry
c87736221ed0: Pull complete
1cc8e0bb44df: Pull complete
54d33bcb37f5: Pull complete
e8afc091c171: Pull complete
b4541f6d3db6: Pull complete
Digest: sha256:8004747f1e8cd820a148fb7499d71a76d45ff66bac6a29129bfdbfdc0154d146
Status: Downloaded newer image for registry:latest
f0084b5985e062b98d1bb5ce93bd9b29ed5f823b8a4a0edf778a98965dfbd4ee
```
- `docker tag ubuntu localhost:5000/ubuntu:prueba`
- `docker push localhost:5000/ubuntu:prueba`
- **nota** *subo la imagen en reg_docker para tener la conf de la estructura son unos 25MB*

## Sección 8: Docker Swarm. Docker en Cluster
### [99. Introducción a Docker Swarm](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12828351#questions)
- Docker funciona de manera independiente, **stand-alone**
- Docker swarm usa el concepto de servicio, una servidor web o una bd
- Un cluster de docker está conformado por:
  - Managers
  - Worker - Nodo que se encarga del trabajo y donde se desplegará el contenedor
  - Cada nodo es una maquina virtual
  - Tendremos varios nodos, un numero n de workers
  - La relación de manager <-> worker es un crossjoin
- Componente que se encargará de una determinada tarea. Bd, app-web, etc
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/782x444/d1e7c268a301df27739ac9b4017ea663/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/792x367/66777dd67636165b2859909e4404e427/image.png)

### [100. Crear un cluster de Docker Swarm](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12828676#questions)
```
λ docker swarm
Commands:
  ca          Display and rotate the root CA
  init        Initialize a swarm
  join        Join a swarm as a node and/or manager
  join-token  Manage join tokens
  leave       Leave the swarm
  unlock      Unlock swarm
  unlock-key  Manage the unlock key
  update      Update the swarm

docker service
Commands:
  create      Create a new service
  inspect     Display detailed information on one or more services
  logs        Fetch the logs of a service or task
  ls          List services
  ps          List the tasks of one or more services
  rm          Remove one or more services
  rollback    Revert changes to a service's configuration
  scale       Scale one or multiple replicated services
  update      Update a service
```
- crear cluster: `docker warm init`
- si quiero indicar una ip concreta: `docker swarm init --advertise-addr 192.168.1.129`
```
λ docker swarm init --advertise-addr 192.168.1.129
Swarm initialized: current node (g78vzintlij8vbkyxjgtxt08i) is now a manager.
To add a worker to this swarm, run the following command:
  docker swarm join --token SWMTKN-1-5l1s7487qzpt5h5on81ow2goyl8ikhcnki9pyv85zogwpbk12s-b5m17qdaqqf8h365fo8pwlvrb 192.168.1.129:2377
To add a manager to this swarm, run 'docker swarm join-token manager' 
and follow the instructions.
```
- Los nodos del cluster deben de tener una ip fija, configuro la ip de mi tarjeta de red por cable
- `docker info`
  - Se puede ver en la parte de Sarm
  ```
  Swarm: active
  NodeID: g78vzintlij8vbkyxjgtxt08i
  Is Manager: true
  ClusterID: 6yn6kxpzwwyrze87757z6bdh8
  Managers: 1
  Nodes: 1
  Default Address Pool: 10.0.0.0/8
  SubnetSize: 24
  ...
  Root Rotation In Progress: false
  Node Address: 192.168.1.129
  Manager Addresses:
   192.168.1.129:2377
  ```
- comprobar comando para unirse al cluster:
  - `docker swarm join-token`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1093x63/4392b0b716c614018acd33342a9711f7/image.png)

### [101. Añadir nodos al cluster](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12828824#questions)
- **Nota!** para esta sección se necesita varias maquinas virtuales :(
- En el ejemplo son 3 nodos. Se ha conectado por ssh
- Usare las pantalla del curso
- Arrancar el cluster: `nodo1: docker swarm init --advertise-addr 192.168.80.217`
  - Ya tenemos el cluster funcionando (de momento solo con el maestro)
- Arrancar esclavos:
- `nodo2: docker swarm join --token SWMTKN-hash 192.168.80.217`
- `nodo3: docker swarm join --token SWMTKN-hash 192.168.80.217`
- `docker info`
- ![](https://trello-attachments.s3.amazonaws.com/5c0935ef647dd339b9e7f791/5dc83c983b83fa63f035cf35/1f50d486b560ac30851659a6734abfe4/image.png)

### [102. Trabajar con los nodos del cluster](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12828940#questions)
- `docker swarm nodes`
```
Commands:
  ca          Display and rotate the root CA
  init        Initialize a swarm
  join        Join a swarm as a node and/or manager
  join-token  Manage join tokens
  leave       Leave the swarm
  unlock      Unlock swarm
  unlock-key  Manage the unlock key
  update      Update the swarm
```
- `docker node ls`
  - ![](https://trello-attachments.s3.amazonaws.com/5c0935ef647dd339b9e7f791/5dc83c983b83fa63f035cf35/417cdd404cb199bf1e7ab61de71223a5/image.png)
- `docker node inspect --pretty node2`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/814x250/bc13f9d4c65669cb9412568e5a54aa0c/image.png)
- Podemos tener varios manager de respaldo. 
- Vamos a promover el nodo3 como manager como **Reachable**
  - `docker node promote nodo3`
  - ![](https://trello-attachments.s3.amazonaws.com/5c0935ef647dd339b9e7f791/5dc83c983b83fa63f035cf35/2b1a88c69ba7956eb6b52989695394bf/image.png)
- Degradar de manager a worker
  - `docker demote nodo1`
  - `nodo1: docker node ls`  esto ahora daría error pq el comando docker node ls solo se puede ejecutar en managers
- Ahora el **leader** es el nodo3
  - ![](https://trello-attachments.s3.amazonaws.com/5c0935ef647dd339b9e7f791/5dc83c983b83fa63f035cf35/5fdc83d57fc2f45e8a3fa1c673f887cc/image.png)
- Quitar un nodo del cluster `nodo1: docker swarm leave`
  - ![](https://trello-attachments.s3.amazonaws.com/5c0935ef647dd339b9e7f791/5dc83c983b83fa63f035cf35/49349bb0e4c33b951d2440edbef00ae5/image.png)
- El hecho de quitar un nodo del cluster hace que se elimine, para eso se usa:
  - `nodo3: docker node rm nodo1`
  - ![](https://trello-attachments.s3.amazonaws.com/5c0935ef647dd339b9e7f791/5dc83c983b83fa63f035cf35/db00170187ec8d74255f799c47e00c7b/image.png)
- Lo puedo volver a añadir:
  - `nodo3: docker swarm join-token worker` para saber el comando
  - En el nodo1: `docker swarm join --token ....`

### [103. Crear y trabajar con servicios](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12838906#questions)
- `nodo3: docker service create --replicas 1 --name servicio1 alpine ping docker.com`
  - replicas: cuantas veces se va a lanzar en los distintos nodos del cluster
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/892x121/6369d31946a8c4d88518bf9163c66754/image.png)
  - `verify: Service converged`
- `nodo3: docker service ls`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1098x121/913f1947939dcd318ee19f83133aeca8/image.png)
- `nodo3: docker service ps servicio1`
  - Aporta más información
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1189x122/94fd4c9cbc43c96d3aef43a2a76c5d28/image.png)
- `nodo2: docker service ps servicio1` no funciona, por no ser manager
- `nodo2: docker ps`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1053x106/194ff958efe2f8a0bd014faa60a591c5/image.png)
- `nodo3: docker service logs servicio1`
- `nodo3: docker service inspect --pretty servicio1`

### [104. Escalar un servicio](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12839094#questions)
- Escalar es repetir ese servicio varias veces
- Se pueden replicar muchas veces tantas como quisiera
- Cada vez que se lanza un servicio dentro de un entorno se le llama tareas
- `nodo3: docker service scale servicio1=2`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/753x158/0c4539a76816ca06f2a6f8553480136b/image.png)
- `nodo3: docker service ps servicio1`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1047x209/7c92f8a4fbfdf9f11926ddc14d12f490/image.png)
- Otro ejemplo, desde el manager se le indica otras 5 replicas de alpine ping docker.com, y este se balancea de forma homogenea entre todos los nodos
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/955x484/7f7a2801c41c2097fa3df2cea0eb8811/image.png)
- `nodo3: docker service ls`
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1114x124/826b68b4ce5852189edc28543e958593/image.png)

### [105. Borrar un servicio](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12839140#questions)
- Bajar el numero de replicas o tareas
- `nodo3: docker service scale servicio1=3`
  - Este proceso tarda un rato
  - ![](https://trello-attachments.s3.amazonaws.com/5c0935ef647dd339b9e7f791/5dc83c983b83fa63f035cf35/c0fd1970e7834bbb63779ca65dd4cafe/image.png)
- Supongamos que ya no necesito servicio1
  - `nodo3: docker service rm servicio1`
  - El comando no es inmediato, tiene que acabar el proceso en cada contenedor.

## Sección 9: Introducción a Kubernetes
### [106. Introducción a Kubernetes](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12973616#questions)
- Es una introducción básica. (Kubernetes = timonel) o **k8s** *keits*
- Es un orquestador de contenedores. Es similar Swarm pero con mayores posibilidades
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/788x339/f9e985e531d9a3befad6e03bd68181d5/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/772x293/c90d5e65691c73f4762b61921fad5859/image.png)
- ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/809x365/27d4c4c5ecae0ac8e780ff763dd399db/image.png)
### [107. Arquitectura de Kubernetes](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12986974#questions)
- No solo trabaja con docker sino otras arquitecturas
- Necesitaremos un master node
  - Dentro de este un scheduler se planifican los procesos con los que estamos trabajando
  - Controller comprueba que los estados esten funcionando
  - Api-server: son todas las tareas de tipo administración que van a realizarse dentro del cluster
  - TECD almacen clave:valor, mantiene el estado del cluster dentro de esta bd, puede ser interno o externo.
- Nodo:
  - Container runtime: 
  - 

### [108. Tipos de instalación](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/12997456#questions)
-
### [109. Requisitos instalación Minikube](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13007348#questions)
-
### [110. Instalar Kubectl](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13007454#questions)
-
### [111. Instalar y probar minikube](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13007766#questions)
-
### [112. Minikube dashboard](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13015096#questions)
-
### [113. Crear un Deployment y un pod](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13015276#questions)
-
### [114. Kubectl proxy. Acceder al pod](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13015532#questions)
-
### [115. kubectl. Comandos log, describe y exec](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13015728#questions)
-
### [116. Crear un servicio. Exponer un deployment](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13016442#questions)
-
### [117. Escalar un servicio](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/13016502#questions)
-
