# Lo iniciamos con la imagen official de Node 8
FROM node:latest
# Vamos a crear un directorio donde dejar la aplicación Angular
RUN mkdir -p /usr/mi-app
# Nos cambiamos a ese directorio
WORKDIR /usr/mi-app
# Copiamos el paquete json para gestionar las dependencias
COPY package.json /usr/mi-app
# Instalamos esas depndencias
RUN npm install
# Copiamos el código que hemos generado en el punto anterior, al crear la aplicación angular-cli
COPY . /usr/mi-app
# Exponemos el Puerto
EXPOSE 4200
# Arrancamos
CMD ["npm", "start"]