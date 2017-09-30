FROM php:5.6-fpm
COPY ./config/php.ini /usr/local/etc/php/conf.d/
# ADD php-fpm.conf /usr/local/etc/php-fpm.conf
COPY redis-2.2.7.tgz /home/redis.tgz
RUN apt-get update -y && apt-get install -y sendmail libpng-dev && apt-get install -y vim
RUN docker-php-ext-install gd \
&& docker-php-ext-install pdo_mysql \
&& pecl install /home/redis.tgz && echo "extension=redis.so">/usr/local/etc/php/conf.d/redis.ini
ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer
WORKDIR /opt
RUN usermod -u 1000 www-data
VOLUME ["/opt"]
