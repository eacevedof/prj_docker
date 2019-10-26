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

