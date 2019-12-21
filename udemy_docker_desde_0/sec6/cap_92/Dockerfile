FROM node:8.4

COPY . /app

WORKDIR /app

# instalacion de node_modules
RUN ["npm", "install"]

EXPOSE 3000/tcp

CMD ["npm", "start"]