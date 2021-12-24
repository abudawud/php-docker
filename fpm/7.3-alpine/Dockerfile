FROM php:7.3-fpm-alpine

LABEL version="1.0"
LABEL maintainer="abudawud <warishafidz@gmail.com>"

ADD https://raw.githubusercontent.com/abudawud/docker-php-extension-installer/master/install-php-extensions /usr/local/bin/

RUN set -eux; \
	chmod uga+x /usr/local/bin/install-php-extensions;

RUN set -eux; \
	install-php-extensions pdo_mysql mysqli gd zip

