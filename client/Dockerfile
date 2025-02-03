# Usar una imagen oficial de Node.js para construir la app
FROM node:18-alpine AS build

# Establecer el directorio de trabajo
WORKDIR /usr/src/app

# Copiar los archivos de dependencias
COPY client/package*.json ./

# Instalar las dependencias del proyecto
RUN npm install

# Copiar el código fuente de la aplicación
COPY client/ .

# Establecer el argumento para el backend URL (lo recibe como un build argument)
ARG VITE_BACKEND_URL
ENV VITE_BACKEND_URL=$VITE_BACKEND_URL

# Construir la aplicación para producción (generará la carpeta `build`)
RUN npm run build

# Usar Nginx para servir la aplicación estática
FROM nginx:alpine

# Copiar los archivos de la aplicación construida al contenedor Nginx
COPY --from=build /usr/src/app/build /usr/share/nginx/html

# Exponer el puerto en el que Nginx sirve la aplicación
EXPOSE 80

# Comando para arrancar Nginx en el contenedor
CMD ["nginx", "-g", "daemon off;"]
