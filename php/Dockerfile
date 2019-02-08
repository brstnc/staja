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
    service apache2 restart
