FROM abudawud/php-fpm:5.6

LABEL version="1.0"
LABEL maintainer="abudawud <warishafidz@gmail.com>"

COPY instantclient_11_2.tar.xz ./

RUN set -eux; \
	# add dependencie
	apk add libaio libnsl; \
	ln -s /usr/lib/libnsl.so.2 /usr/lib/libnsl.so.1; \
	# extract sources
	docker-php-source extract; \
	tar xJf instantclient_11_2.tar.xz; \
	mv instantclient_11_2 /usr/lib; \
	# setup client
	cd /usr/lib/instantclient_11_2; \
	ln /usr/lib/instantclient_11_2/libclntsh.so.11.1 /usr/lib/libclntsh.so; \
	ln /usr/lib/instantclient_11_2/libocci.so.11.1 /usr/lib/libocci.so; \
	ln /usr/lib/instantclient_11_2/libociei.so /usr/lib/libociei.so; \
	ln /usr/lib/instantclient_11_2/libnnz11.so /usr/lib/libnnz11.so; \
	ln -s libclntsh.so.11.1 libclntsh.so; \
	# setup and install pdo_oci
	docker-php-ext-configure pdo_oci --with-pdo-oci=instantclient,/usr/lib/instantclient_11_2,11.2; \
	docker-php-ext-install pdo_oci; \
	# cleaning
	docker-php-source delete; \
	cd - ; \
	rm instantclient_11_2.tar.xz

