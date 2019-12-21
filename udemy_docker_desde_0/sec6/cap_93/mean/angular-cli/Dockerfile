# Lo iniciamos con la imagen official de Node 8
FROM node:8
# Vamos a crear un directorio donde dejar la aplicación Angular
RUN mkdir -p /usr/mi-app
# Nos cambiamos a ese directorio
WORKDIR /usr/mi-app
# Copiamos el paquete json para gestionar las dependencias
COPY package.json /usr/mi-app
# Instalamos esas depndencias
RUN npm install