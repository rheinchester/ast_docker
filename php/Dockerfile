FROM php:8.0-apache

# we did not install git. intall next time
# also, we didn't install  mysql
# COPY  php-ini  /usr/local/etc/php 
# COPY /usr/local/etc/php php-ini
# COPY  /usr/local/etc/php .

# consider renaming php.ini-production to php.ini
# Don't ever rum `docker-compose up -d --build` on this particular project. It will rebuild the application and get rid of your settings
RUN apt update \
        && apt install -y \
            g++ \
            libicu-dev \
            libpq-dev \
            libzip-dev \
            zip \
            zlib1g-dev \
            git\
        && docker-php-ext-install \
            intl \
            opcache \
            pdo \
            pdo_mysql \
            pgsql 

#  remember to docker-php-ext-install mysqli
# chown -R www-data:www-data /var/www/laravel_docker
#  apt-get install net-tools
WORKDIR /var/www/laravel_docker

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# RUN ls -la /usr/local/etc/php/