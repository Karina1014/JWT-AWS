# Establecer la imagen base de Node.js
FROM node:18-alpine

# Establecer el directorio de trabajo dentro del contenedor
WORKDIR /usr/src/app

# Copiar los archivos package.json y package-lock.json desde la carpeta server al contenedor
COPY server/package*.json ./

# Instalar las dependencias
RUN npm install

# Copiar el resto del código de la aplicación desde la carpeta server al contenedor
COPY server/ .

# Exponer el puerto en el que el servicio escucha (3011 en este caso)
EXPOSE 3011

# Ejecutar la aplicación usando node
CMD ["node", "src/server.js"]
