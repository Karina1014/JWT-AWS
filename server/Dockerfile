# Establecer la imagen base de Node.js
FROM node:18-alpine

# Establecer el directorio de trabajo dentro del contenedor
WORKDIR /usr/src/app

# Copiar los archivos package.json y package-lock.json (si existe) al contenedor
COPY package*.json ./

# Instalar las dependencias
RUN npm install

# Copiar el resto del código de la aplicación al contenedor
COPY . ./

# Exponer el puerto en el que el servicio escucha (puedes usar 3011 como en tu caso)
EXPOSE 3011

# Establecer la variable de entorno para que la app se ejecute en modo desarrollo (si es necesario)
# ENV NODE_ENV=development

# Ejecutar la aplicación usando node
CMD ["node", "src/server.js"]
