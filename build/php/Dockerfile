FROM php:8.0-fpm

COPY ./build/php/php.ini /usr/local/etc/php/conf.d/docker-php-config.ini

COPY ./build/php/xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

COPY ./app /var/www/symfony

RUN apt-get update && apt-get install -y

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    g++ \
    procps \
    libzip-dev \
    libxslt1-dev \
    libpng-dev \
    libonig-dev \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN docker-php-ext-install \
    pdo pdo_mysql zip xsl gd intl mbstring

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

WORKDIR /var/www/symfony

RUN composer install

EXPOSE 9003