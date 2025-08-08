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


# ставим необходимые для нормальной работы модули
RUN apt-get update && apt-get install -y \
        curl \
        wget \
        git \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
	libpng-dev \
	libonig-dev \
	libzip-dev \
	libmcrypt-dev \
        && pecl install mcrypt-1.0.3 \
	&& docker-php-ext-enable mcrypt \
        && docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip \
	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
        && docker-php-ext-install -j$(nproc) gd 
 
# Устанавливаем Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
 
WORKDIR /data/mysite.local
 
VOLUME /data
 
CMD ["php-fpm"]