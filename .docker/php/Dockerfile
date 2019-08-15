FROM php:7.2-fpm

RUN apt-get update \
    && apt-get install -y --no-install-recommends nano curl git build-essential wget zip unzip iproute2

#RUN apt-get install -y --no-install-recommends iproute2 iputils-ping

RUN docker-php-ext-install pdo pdo_mysql

COPY php.ini /usr/local/etc/php

RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && \
   mv composer.phar /usr/local/bin/composer

WORKDIR /var/www/html

EXPOSE 9000
CMD ["php-fpm"]