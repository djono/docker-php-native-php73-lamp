FROM php:7.3-fpm-alpine
RUN apk update; \
    apk upgrade;
RUN docker-php-ext-install mysqli mbstring pdo_mysql
RUN apk add libpq-dev \
    && docker-php-ext-configure pgsql --with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo pdo_pgsql pgsql
RUN apk add freetype libpng libjpeg-turbo freetype-dev libpng-dev libjpeg-turbo-dev
#RUN docker-php-ext-install -j$(nproc) iconv 
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 
RUN docker-php-ext-install -j$(nproc) gd
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
COPY php.ini /usr/local/etc/php/php.ini
