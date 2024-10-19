# Dockerfile para React
FROM node:16

# Establecer el directorio de trabajo
WORKDIR /usr/src/app

# Copiar package.json y package-lock.json
COPY ./reminder-frontend/package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el resto del código
COPY ./reminder-frontend/ .

# Construir la aplicación
RUN npm run build

# Exponer el puerto 3000
EXPOSE 3000

# Comando para iniciar el servidor
CMD ["npm", "start"]