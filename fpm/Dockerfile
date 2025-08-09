FROM php:7.4-fpm

# Установите необходимые расширения
RUN apt-get update && \
    apt-get install -y \
    libonig-dev \
    libxml2-dev \
    zlib1g-dev

RUN docker-php-ext-install pdo pdo_mysql
