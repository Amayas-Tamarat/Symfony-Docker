FROM php:8.4-fpm

COPY docker/php/php.ini /usr/local/etc/php/conf.d/docker-php-config.ini

RUN apt-get update && apt-get install -y \
    gnupg \
    g++ \
    make \
    build-essential \
    procps \
    openssl \
    git \
    unzip \
    zlib1g-dev \
    libzip-dev \
    libfreetype6-dev \
    libpng-dev \
    libjpeg-dev \
    libicu-dev  \
    libonig-dev \
    libxslt1-dev \
    acl \
    && echo 'alias sf="php bin/console"' >> ~/.bashrc

RUN docker-php-ext-configure gd --with-jpeg --with-freetype

RUN docker-php-ext-install \
    pdo pdo_mysql zip xsl gd intl opcache exif mbstring

# Set timezone
#ENV TIMEZONE = Europe/Paris
#RUN ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && echo ${TIMEZONE} > /etc/timezone \
#    && printf '[PHP]\ndate.timezone = "%s"\n', ${TIMEZONE} > /usr/local/etc/php/conf.d/tzone.ini \
#    && "date"

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN mkdir -p /var/www/symfony && chmod -R 777 /var/www/symfony
WORKDIR /var/www/symfony

RUN curl -sS https://get.symfony.com/cli/installer | bash \
    && mkdir -p /root/.config/symfony-cli \
    && ([ -d /root/.symfony5 ] && mv /root/.symfony5/* /root/.config/symfony-cli/ && rm -rf /root/.symfony5 || true) \
    && mv $(find /root -name "symfony" -type f 2>/dev/null | head -1) /usr/local/bin/symfony
