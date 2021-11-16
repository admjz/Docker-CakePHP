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
RUN mv /bin/sh /bin/sh_tmp && ln -s /bin/bash /bin/sh
RUN echo "alias ll='ls -la'" >> ~/.bashrc
RUN source ~/.bashrc
RUN rm /bin/sh && mv /bin/sh_tmp /bin/sh