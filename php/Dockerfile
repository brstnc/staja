# AUTHOR: Omer Erol
# CREATED FOR BEYAZNET PROJECTS

ARG PHP_VERSION
FROM php:$PHP_VERSION

MAINTAINER Omer Erol omerol@live.com

# General environments for php server
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y vim && \
    docker-php-ext-install pdo_mysql && \
    a2enmod rewrite && \
    a2enmod ssl && \
    service apache2 restart && \
    mkdir -p /etc/apache2/ssl

# XDEBUG installation
RUN apt-get install -y wget && \
    wget http://xdebug.org/files/xdebug-2.7.0RC2.tgz && \
    tar -xvzf xdebug-2.7.0RC2.tgz && \
    cd xdebug-2.7.0RC2 && \
    phpize && \
    ./configure && \
    make && \
    cp modules/xdebug.so /usr/local/lib/php/extensions/no-debug-non-zts-20180731 && \
    echo "zend_extension = /usr/local/lib/php/extensions/no-debug-non-zts-20180731/xdebug.so" >> /usr/local/etc/php/php.ini
