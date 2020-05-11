FROM php:7.4-fpm
WORKDIR /var/www
RUN apt-get update && apt-get install -y wget git unzip \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
	&& docker-php-ext-install mysqli \
	&& docker-php-ext-enable mysqli \ 
	&& docker-php-ext-enable opcache
ADD ./php.ini /usr/local/etc/php/php.ini
ENV COMPOSER_ALLOW_SUPERUSER 1
RUN wget https://getcomposer.org/installer -O - -q \
    | php -- --install-dir=/bin --filename=composer --quiet