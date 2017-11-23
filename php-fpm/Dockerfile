FROM php:7.0.13-fpm
#FROM php:5.6.30-fpm
#FROM php:5.4-fpm

MAINTAINER Stéphane Koeberlé <sk@link2b.fr>

RUN docker-php-ext-install pdo_mysql mysqli

#Install XDEBUG
RUN yes | pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini

CMD /bin/bash

CMD ["php-fpm"]
