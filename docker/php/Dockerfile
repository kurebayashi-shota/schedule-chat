# docker/php/Dockerfile
FROM php:8.2-apache

# 必要なモジュールをインストール
RUN apt-get update && apt-get install -y \
    libzip-dev zip unzip \
    && docker-php-ext-install pdo pdo_mysql zip \
    && apt-get install -y libpq-dev \
    && docker-php-ext-install pdo_pgsql

# Apache設定ファイルをコピー
COPY ./docker/apache/default.conf /etc/apache2/sites-available/000-default.conf

# Laravel用にmod_rewrite有効化
RUN a2enmod rewrite

# 作業ディレクトリを指定
WORKDIR /var/www/html
COPY ./app /var/www/html

RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html
