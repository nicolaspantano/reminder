# Dockerfile para Symfony
FROM php:8.1-fpm

# Instalar dependencias
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    unzip \
    git \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd

# Establecer el directorio de trabajo
WORKDIR /var/www/symfony

# Copiar el composer.lock y composer.json
COPY /reminder-backend/composer.json /reminder-backend/composer.lock ./

# Instalar Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copiar el resto del código
COPY ./reminder-backend/ .

# Instalar dependencias de PHP
RUN composer install

# Exponer el puerto 9000
EXPOSE 9000

# Comando para iniciar el servidor
CMD ["php-fpm"]