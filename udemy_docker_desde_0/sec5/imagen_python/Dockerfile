FROM ubuntu
RUN apt-get update
# no puede haber nada interactivo por eso el flag -y sino daría error
RUN apt-get install -y python
# con && evitamos que se cree una capa por RUN 
RUN echo 1.0 >> /etc/version && apt-get install -y git \
    && apt-get install -y iputils-ping
