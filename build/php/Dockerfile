FROM php:8.0-fpm

COPY ./build/php/php.ini /usr/local/etc/php/conf.d/docker-php-config.ini

RUN apt-get update && apt-get install -y

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    g++ \
    procps \
    libzip-dev \
    libxslt1-dev \
    libpng-dev \
    libonig-dev

RUN docker-php-ext-install \
    pdo pdo_mysql zip xsl gd intl mbstring

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

WORKDIR /var/www/symfony