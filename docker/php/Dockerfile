FROM php:7.2-fpm

RUN apt-get update && apt-get install -y curl \ 
    vim \
    libpq-dev \
    libxml2-dev \
    openssl \
    git-all


RUN docker-php-ext-install \
    pdo_mysql \
    pdo_pgsql \
    bcmath \
    soap

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer
RUN php -r "unlink('composer-setup.php');"

WORKDIR /opt/contextos-api

EXPOSE 8000 80