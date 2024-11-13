FROM php:8.2.25-fpm-alpine3.20

RUN apk --no-cache add libmagic ghostscript
RUN --mount=type=bind,from=mlocati/php-extension-installer:latest,source=/usr/bin/install-php-extensions,target=/usr/local/bin/install-php-extensions \
      install-php-extensions mysqli soap intl exif gd sockets xsl xml zip pdo bcmath mbstring imagick opcache curl @composer-2

COPY www.conf /usr/local/etc/php-fpm.d/www.conf

WORKDIR /var/www/html
