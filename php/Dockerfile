FROM php:8.2.9-fpm-alpine3.18

WORKDIR /var/www/inertia

RUN apk update && apk upgrade && apk add \
    build-base \
    git \
    curl \
    zip \
    libzip-dev \
    libpq-dev \
    unzip \
    nano \
    nodejs \
    npm

RUN docker-php-ext-install pdo pdo_mysql zip exif pcntl

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
RUN npm i -g pnpm

USER root

RUN chmod 777 -R /var/www/inertia
