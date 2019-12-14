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
COPY add_user.sh .

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

## ARG
# nos permite pasar variables en la construcción
# no tengo la obligacion de aplicar valor a dir2
ARG dir2
RUN mkdir $dir2
ARG user
ENV user_docker $user
RUN /datos1/add_user.sh

ENTRYPOINT ["/bin/bash"]
