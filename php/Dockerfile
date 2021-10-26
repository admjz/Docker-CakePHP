FROM php:7.1-fpm
COPY php.ini /usr/local/etc/php/
RUN apt-get update && \
  apt-get install -y vim &&\
  apt-get install -y unzip &&\
  apt-get install -y libicu-dev &&\
  docker-php-ext-install intl &&\
  docker-php-ext-install pdo_mysql &&\
  curl -sS https://getcomposer.org/installer | php &&\
  mv composer.phar /usr/local/bin/composer