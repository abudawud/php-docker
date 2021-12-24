FROM php:7.3-fpm-alpine

LABEL version="1.0"
LABEL maintainer="abudawud <warishafidz@gmail.com>"

ADD https://raw.githubusercontent.com/abudawud/docker-php-extension-installer/master/install-php-extensions /usr/local/bin/
ADD https://getcomposer.org/composer-stable.phar /usr/local/bin/composer

RUN set -eux; \
	apk add rsync git; \
	chmod uga+x /usr/local/bin/install-php-extensions /usr/local/bin/composer && sync;

RUN set -eux; \
    install-php-extensions gd zip 
