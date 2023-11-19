# PHP Upstream Builder

CI/CD Job to prebuild upstream PHP images (binary distribution of https://hub.docker.com/_/php).

Images are build once per week with newest GA version of PHP for each supported realease.

## Example usage

CLI:
```
docker run --rm --pull always -it wyga/php-upstream:8.2-fpm-alpine
```

Dockerfile
```
FROM wyga/php-upstream:8.2-fpm-alpine
RUN install-php-extensions pgsql && \
    docker-php-ext-enable-xdebug
```

## Registries

 - docker.io

## Suported PHP versions

  - 8.0.x
  - 8.1.x
  - 8.2.x

## Supported image flavors

  - fpm-alpine

## Included PHP modules

### Enabled

  - bcmath
  - bz2
  - calendar
  - ctype
  - curl
  - date
  - dom
  - exif
  - fileinfo
  - filter
  - ftp
  - gd
  - gettext
  - gmp
  - hash
  - iconv
  - intl
  - json
  - libxml
  - mbstring
  - mysqli
  - mysqlnd
  - openssl
  - pcre
  - pdo_mysql
  - pdo_sqlite
  - posix
  - random
  - readline
  - session
  - SimpleXML
  - sodium
  - SPL
  - sqlite3
  - tokenizer
  - xml
  - xmlreader
  - xmlwriter
  - OPcache
  - zip
  - zlib

### Availible

  - mcrypt
  - memcache
  - memcached
  - mongodb
  - redis
  - xdebug
  - yaml

Can be enabled via this commands:

```
docker-php-ext-enable-mcrypt
docker-php-ext-enable-memcached 
docker-php-ext-enable-memcache
docker-php-ext-enable-mongodb 
docker-php-ext-enable-redis
docker-php-ext-enable-xdebug 
docker-php-ext-enable-yaml
```

### Additional exensions

More extensions can be installed on demand with command:

```
install-php-extensions
```
See: https://github.com/mlocati/docker-php-extension-installer#supported-php-extensions

## Supported platforms

  - linux/amd64
  - linux/arm64

More info:
```
regctl manifest get wyga/php-upstream:8.2-fpm-alpine
regctl manifest get --platform linux/amd64 wyga/php-upstream:8.2-fpm-alpine
```
See: https://github.com/regclient/regclient

## Settings

Make sure you set Timeout value to at least 8 hours.

```
Settings->CI/CD->General pipelines->Timeout
```
