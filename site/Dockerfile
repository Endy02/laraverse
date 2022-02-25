FROM php:8.0-apache

# Quelques library necessaires
RUN apt-get update
RUN apt-get install -y --no-install-recommends locales apt-utils git g++ libicu-dev zlib1g-dev libpng-dev libzip-dev libyaml-dev

# On envoie le nom du serveur à apache, c'est avec ça que l'on appelera nos pages
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

# les locales, toujours utiles
RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    echo "fr_FR.UTF-8 UTF-8" >> /etc/locale.gen && \
    locale-gen

# on télécharge et deplace le composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Quelques extesnions de php utiles
RUN docker-php-ext-configure intl
RUN docker-php-ext-install pdo pdo_mysql gd opcache intl zip calendar
RUN pecl install apcu && docker-php-ext-enable apcu
RUN pecl install yaml-2.1.0

# We add a user with the gid/uid as our local user
# replace "fujyn" by your local user 
RUN addgroup --system fujyn --gid 1000 && adduser --system fujyn --uid 1000 --ingroup www-data

# TODO : Review premission when coding (vs code ask for permission when your start edit a file create with php artisan command)

RUN a2enmod rewrite

WORKDIR /var/www/