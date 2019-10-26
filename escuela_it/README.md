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
  - Docker
  - Container-1,...,Container-n
    - Para cada Container-i
    - Bin/Labs
    - App-i
  


## Comandos Docker

# 
