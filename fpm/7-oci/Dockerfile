FROM abudawud/php-fpm:7

LABEL version="1.0"
LABEL maintainer="abudawud <warishafidz@gmail.com>"

RUN set -eux; \
	# add dependencie
	apk add libaio libnsl; \
	ln -s /usr/lib/libnsl.so.2 /usr/lib/libnsl.so.1; \
	# extract sources
	docker-php-source extract; \
	wget https://raw.githubusercontent.com/abudawud/php-docker/master/fpm/5.6-oci/instantclient_11_2.tar.xz; \
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

 ENV ORACLE_BASE=/usr/lib/instantclient_11_2 \
	LD_LIBRARY_PATH=/usr/lib/instantclient_11_2 \
	TNS_ADMIN=/usr/lib/instantclient_11_2 \
	ORACLE_HOME=/usr/lib/instantclient_11_2
