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

## ENV
ENV dir=/data dir1=/data1
RUN mkdir $dir && mkdir $dir1

## ENTRYPOINT
# ENTRYPOINT ["/bin/bash","-c","/datos1/welcome.sh"] ??? 
# esto da error pq no existe welcome.sh y no deja entrar al bash

ENTRYPOINT ["/bin/bash"]
