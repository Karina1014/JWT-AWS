# Construcción de la app con Node.js
FROM node:18-alpine AS build

WORKDIR /app

# Copiar solo los archivos de dependencias desde client/
COPY client/package.json client/package-lock.json ./
RUN npm install --frozen-lockfile

# Copiar el resto del código
COPY client ./
RUN npm run dev
