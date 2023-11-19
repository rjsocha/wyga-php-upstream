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
RUN enable-php-extensions xdebug opcache mysqli gd
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

  - bcmath
  - bz2
  - calendar
  - exif
  - gd
  - gettext
  - gmp
  - imap
  - intl
  - ldap
  - mcrypt
  - memcache
  - memcached
  - mongodb
  - mysqli
  - opcache
  - pcntl
  - pdo_mysql
  - pgsql
  - redis
  - sockets
  - xdebug
  - xsl
  - yaml
  - zip

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
