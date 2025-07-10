FROM php:8.2-fpm

# Instalar extensões necessárias, incluindo intl, mysqli e pdo_mysql para MySQL
RUN apt-get update && apt-get install -y \
    libonig-dev \
    libzip-dev \
    unzip \
    libicu-dev \
    && docker-php-ext-install intl pdo_mysql mysqli mbstring zip \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Copiar o php.ini customizado (você já tem)
COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html
