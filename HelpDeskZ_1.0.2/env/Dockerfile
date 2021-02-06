FROM php:5.5-apache
COPY --chown=www-data:www-data HelpDeskZ-1.0/ /var/www/html/support/

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
        libmcrypt-dev \
        libpng12-dev \
        libjpeg-dev \
        libpng-dev \
    && docker-php-ext-install iconv mcrypt \
    && docker-php-ext-configure gd \
        --enable-gd-native-ttf \
        --with-freetype-dir=/usr/include/freetype2 \
        --with-png-dir=/usr/include \
        --with-jpeg-dir=/usr/include \
    && docker-php-ext-install gd \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install mysql mysqli \
    && docker-php-ext-install zip \
    && docker-php-ext-enable gd 

# avoid reconfig 'AllowOverride'
RUN mv /etc/apache2/conf-enabled/docker-php.conf /etc/apache2/conf-enabled/docker-php.conf.bak

# redirect php error to stderr
RUN COPY php-enable-errlog.ini /usr/local/etc/php/conf.d/
