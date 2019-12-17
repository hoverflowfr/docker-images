FROM php:7.3-cli

ARG composer_url=https://raw.githubusercontent.com/composer/getcomposer.org/76a7060ccb93902cd7576b67264ad91c8a2700e2/web/installer

ENV COMPOSER_ALLOW_SUPERUSER=1
ENV PATH=/root/.composer/vendor/bin:$PATH

# Install basic librairies and PHP extensions
RUN apt-get update && apt-get install -y --no-install-recommends \
  curl git apt-utils python3-dev python3-pip python3-setuptools unzip \
  zlib1g-dev libzip-dev libwebp-dev libjpeg-dev libpng-dev libz-dev libxpm-dev \
  && pip3 install awscli \
  && docker-php-ext-install zip \
  && docker-php-ext-install bcmath \
  && docker-php-ext-install gd \
  && docker-php-ext-install exif \
  && rm -rf /var/lib/apt/lists/* \
  && apt-get clean

# Install Composer & Vapor CLI
RUN curl -o installer "$composer_url" \
  && php installer --install-dir=/usr/local/bin --filename=composer \
  && composer global require laravel/vapor-cli
