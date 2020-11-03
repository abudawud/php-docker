FROM abudawud/php-fpm:7

LABEL version="1.0"
LABEL maintainer="abudawud <warishafidz@gmail.com>"

RUN set -eux; \
	## install extension
	install-php-extensions gd zip pdo_pgsql pgsql ldap;

