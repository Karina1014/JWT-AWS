# Dockerfile

# Establecer la imagen base de Node.js
FROM node:18-alpine

# Establecer el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copiar los archivos package.json y package-lock.json al contenedor
COPY package*.json ./

# Instalar las dependencias
RUN npm install

# Copiar el resto del código de la aplicación
COPY . .

# Exponer el puerto en el que la aplicación corre (3000 por defecto)
EXPOSE 3000

# Comando para iniciar la aplicación en desarrollo
CMD [ "npm", "run", "dev" ]
