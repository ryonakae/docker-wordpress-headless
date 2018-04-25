FROM wordpress:4.9-php7.2-fpm-alpine

# 不足してるPHPライブラリをインストール
RUN apk update && apk add \
  libjpeg-turbo-dev \
  libpng-dev

# apkでダウンロードしたファイルを削除
RUN rm -rf /var/cache/apk/*

# PHPの拡張をインストール
RUN docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr
RUN docker-php-ext-install gd pdo pdo_mysql mysqli mbstring
