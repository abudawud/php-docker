FROM php:5.6-fpm-alpine

LABEL version="1.0"
LABEL maintainer="abudawud <warishafidz@gmail.com>"

ADD https://raw.githubusercontent.com/abudawud/docker-php-extension-installer/master/install-php-extensions /usr/local/bin/
ADD https://getcomposer.org/composer-stable.phar /usr/local/bin/composer

RUN set -eux; \
	chmod uga+x /usr/local/bin/install-php-extensions /usr/local/bin/composer && sync; \
	## install extension
	install-php-extensions gd zip pdo_pgsql pgsql ldap;

