FROM php:8.3-fpm

RUN apt-get update && apt-get install -y \
    libonig-dev \
    libzip-dev \
    unzip \
    libicu-dev \
    gettext \
    libgettextpo-dev \
    curl \
    git \
    && docker-php-ext-install intl pdo_mysql mysqli mbstring zip gettext \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Instalar Composer
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html
