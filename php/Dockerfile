FROM php:7.1-fpm
COPY ./config/php.ini /usr/local/etc/php/conf.d/
COPY redis-3.1.4.tgz /home/redis.tgz

# ADD php-fpm.conf /usr/local/etc/php-fpm.conf
RUN apt-get update \
&& apt-get install -y \
 sendmail \
 libpng-dev \
 vim \
 git
# Install phpredis
# RUN git clone -b php7 https://github.com/phpredis/phpredis.git /usr/src/php/ext/redis \
#   && docker-php-ext-install redis
RUN docker-php-ext-install gd \
&& docker-php-ext-install pdo_mysql \
&& pecl install /home/redis.tgz && echo "extension=redis.so">/usr/local/etc/php/conf.d/redis.ini
ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer
WORKDIR /opt
RUN usermod -u 1000 www-data
VOLUME ["/opt"]
