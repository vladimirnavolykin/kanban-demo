FROM php:8.1-fpm

WORKDIR /var/www/

RUN apt-get -y update

# linux tools install
RUN apt-get -y install git
RUN git config --global --add safe.directory /var/www/html
RUN apt-get -y install wget
RUN apt-get -y install procps
RUN apt-get -y install htop
RUN apt-get -y install vim

# php ext install
RUN docker-php-ext-install ctype
RUN docker-php-ext-install iconv
RUN docker-php-ext-install pdo
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install pcntl
RUN docker-php-ext-install sockets

RUN pecl install xdebug && docker-php-ext-enable xdebug

# composer install
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

#Additional .ini files $PHP_INI_DIR = /usr/local/etc/php
COPY ./conf.d/* ${PHP_INI_DIR}/conf.d
