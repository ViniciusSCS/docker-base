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
    libxml2-dev \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libssl-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install intl pdo_mysql mysqli mbstring zip gettext xml gd \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Instalar Composer
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html
