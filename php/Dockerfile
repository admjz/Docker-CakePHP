FROM php:7.4-fpm
COPY php.ini /usr/local/etc/php/
RUN apt-get update && \
  apt-get install -y vim &&\
  apt-get install -y unzip &&\
  apt-get install -y libicu-dev &&\
  docker-php-ext-install intl &&\
  docker-php-ext-install pdo_mysql
