FROM php:7.4-fpm

WORKDIR /app

# install dependencies
RUN apt-get update && apt-get install -y \
    zip \
    libzip-dev

# install zip/unzip extensions
RUN pecl install zip \
    && docker-php-ext-enable zip

# install mongodb ext
RUN pecl install mongodb \
    && docker-php-ext-enable mongodb

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

EXPOSE 9000

CMD composer install && php-fpm -R
