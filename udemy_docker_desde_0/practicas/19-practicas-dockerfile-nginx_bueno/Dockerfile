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