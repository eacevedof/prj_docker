# prj_docker

## Indice
- [Docker para desarrolladores - Jesus Matíz](https://github.com/eacevedof/prj_docker/tree/master/jesus_matiz_docker_para_dev#youtube-playlist---presentaci%C3%B3n-del-curso-docker-para-desarrolladores---jes%C3%BAs-matiz)
- [Laravel + MySql con Docker Despliegue a Produccion - Jesus Matíz](https://github.com/eacevedof/prj_docker/tree/master/jesus_matiz#youtube---laravel--mysql-con-docker-despliegue-a-produccion---jesus-mat%C3%ADz)
- [Curso Docker - Escuela It](https://github.com/eacevedof/prj_docker/tree/master/escuela_it#youtube---curso-docker)
- [Docker - Jesus Conde](https://github.com/eacevedof/prj_docker/tree/master/jesus_conde#youtube-playlist---curso-docker-jesus-conde)

## Notas.
- ~~Para arrancar docker en windows hay que lanzar el **Docker Quickstar Terminal** en modo administrador~~
- ~~**`<programs>\git-bash.exe --login -i "<programs>\docker-toolbox\start.sh"`**~~
- ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/300x160/4fa986b5a080f668ffe7ca1332d1f509/image.png)
- Esto resolvió el problema (no del todo)
  - Realmente habia que ejecutar **Docker desktop** al lanzar **DD** tarda unos 2 minutos el arranque completo
  - El terminal no hace falta ejecutarlo en *modo administrador*
  - > Despues ya se puede ejecutar **`docker images`**
  - ![](https://trello-attachments.s3.amazonaws.com/5db43f16df811534517445ec/708x149/ee3dca00349421676434dea9d82e791c/image.png)
```
docker images

error during connect: 
Post http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.40/build?buildargs=%7B%7D&cachefrom=%5B%5D&cgroupparent=
&cpuperiod=0&cpuquota=0&cpusetcpus=&cpusetmems=&cpushares=0&dockerfile=Dockerfile&labels=%7B%7D
&memory=0&memswap=0&networkmode=default&rm=1&session=gotkwtadito89qvwblrm5qk7s&shmsize=0&target=
&ulimits=null&version=1: 
open //./pipe/docker_engine: 
El sistema no puede encontrar el archivo especificado. 
In the default daemon configuration on Windows, the docker client must be run elevated to connect. 
This error may also indicate that the docker daemon is not running.
```
- **Running :)**
```js
yo@my_pc MINGW64 /<project>/escuela_it (master)
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

yo@my_pc MINGW64 /<project>/escuela_it (master)
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
<none>              <none>              cc2abdb57bab        7 minutes ago       159MB
ubuntu              19.10               09604a62a001        8 days ago          72.9MB

yo@my_pc MINGW64 /<project>/escuela_it (master)
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

yo@my_pc MINGW64 /<project>/escuela_it (master)
$
```