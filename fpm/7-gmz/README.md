## php-fpm:5.6-glpz

A Docker image based on php:5.6-fpm-alpine (Official image) that shiped with some extensions and tools.

## Extension

- GD
- LDAP
- PGSQL `pdo_pgsql and pgsql`
- ZIP

## Tools

- composer
- install-php-extensions, refer to [docker-php-extension-installer](https://github.com/mlocati/docker-php-extension-installer)

## Size

```sh
$ docker images | grep php-fpm:5.6-glpz
abudawud/php-fpm                   5.6-glpz            e494336edbd0        About a minute ago   74.3MB

```

