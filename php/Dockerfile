FROM php:7.4-fpm

# Установка зависимостей
RUN apt-get update && \
    apt-get install -y \
    libonig-dev \
    libxml2-dev \
    zlib1g-dev \
    curl \
    zip \
    unzip

# Установка расширений PHP
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-enable pdo pdo_mysql
