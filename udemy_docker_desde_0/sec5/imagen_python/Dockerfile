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


