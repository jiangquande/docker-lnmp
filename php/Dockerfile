FROM php:7.1-fpm

MAINTAINER jiangqd <5050781913@qq.com>

RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev  \
    && rm -rf /var/lib/apt/lists/* \
    && docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr \
    && docker-php-ext-install gd pdo_mysql zip opcache
RUN pecl install redis-4.0.1 swoole \
    && docker-php-ext-enable redis swoole

