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

CMD ["/bin/bash"]


