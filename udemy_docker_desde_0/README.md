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
  - Monta un contenedor de ubuntu y accede por shell
- **docker run busybox**
- **docker ps**
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1080x99/20a0b941a0c4d9bba1f08a6ac5be1deb/image.png)
- **docker ps -a -f name=busy**
  - ![](https://trello-attachments.s3.amazonaws.com/5dc83c983b83fa63f035cf35/1025x52/82e71292be614884fbb23e90b090bf43/image.png)
  
### [20. Crear un contenedor interactivo](https://www.udemy.com/course/aprende-docker-desde-cero/learn/lecture/9626196#questions)
- Vamos a crear un contenedor un poco más amplio
- Sistema operativo minificado **Bear bone**?? *consultado en udemy*
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
- 
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
