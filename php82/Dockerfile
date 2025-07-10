FROM php:8.2-fpm

RUN apt-get update && apt-get install -y \
    libonig-dev \
    libzip-dev \
    unzip \
    libicu-dev \
    gettext \
    libgettextpo-dev \
    && docker-php-ext-install intl pdo_mysql mysqli mbstring zip gettext \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html