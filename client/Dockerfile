# Construcción de la app con Node.js
FROM node:18-alpine AS build

WORKDIR /app

# Copiar solo los archivos necesarios para instalar dependencias
COPY package.json package-lock.json ./
RUN npm install --frozen-lockfile

# Copiar el resto del código y generar el build
COPY . .
RUN npm run build

# ----------------------------------------------
# Fase final: Servir la app con Nginx
FROM nginx:alpine

# Copiar los archivos estáticos generados por Vite
COPY --from=build /app/dist /usr/share/nginx/html

# Exponer el puerto 80 (por defecto en Nginx)
EXPOSE 80

# Iniciar Nginx
CMD ["nginx", "-g", "daemon off;"]
