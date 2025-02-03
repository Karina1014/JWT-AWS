# Establecer la imagen base de Node.js
FROM node:18-alpine

# Establecer el directorio de trabajo dentro del contenedor
WORKDIR /usr/src/app

# Copiar los archivos package.json y package-lock.json (si existe) al contenedor
COPY server/package*.json ./

# Instalar las dependencias
RUN npm install

# Copiar el resto del código de la aplicación al contenedor
COPY . .

# Establecer los argumentos de las variables sensibles
ARG MONGODB_URI
ARG JWT_SECRET
ARG SMTP_USER
ARG SMTP_PASS
ARG SENDER_EMAIL
ARG REACT_APP_RDS_HOST
ARG REACT_APP_RDS_PORT
ARG REACT_APP_RDS_DATABASE
ARG REACT_APP_RDS_USER
ARG REACT_APP_RDS_PASSWORD

# Establecer las variables de entorno para el contenedor
ENV MONGODB_URI=$MONGODB_URI
ENV JWT_SECRET=$JWT_SECRET
ENV SMTP_USER=$SMTP_USER
ENV SMTP_PASS=$SMTP_PASS
ENV SENDER_EMAIL=$SENDER_EMAIL
ENV REACT_APP_RDS_HOST=$REACT_APP_RDS_HOST
ENV REACT_APP_RDS_PORT=$REACT_APP_RDS_PORT
ENV REACT_APP_RDS_DATABASE=$REACT_APP_RDS_DATABASE
ENV REACT_APP_RDS_USER=$REACT_APP_RDS_USER
ENV REACT_APP_RDS_PASSWORD=$REACT_APP_RDS_PASSWORD

# Exponer el puerto en el que el servicio escucha
EXPOSE 3011

# Ejecutar la aplicación usando node
CMD ["node", "src/server.js"]
