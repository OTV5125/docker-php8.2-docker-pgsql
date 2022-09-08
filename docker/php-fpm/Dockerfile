FROM php:8.2-rc-fpm
RUN apt-get update && apt-get install -y \
curl \
wget \
git \
libfreetype6-dev \
libjpeg62-turbo-dev \
libpng-dev \
libonig-dev \
libzip-dev \

&& docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip \
&& docker-php-ext-configure gd --with-freetype --with-jpeg \
&& docker-php-ext-install -j$(nproc) gd

ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini

WORKDIR /var/www

CMD ["php-fpm"]