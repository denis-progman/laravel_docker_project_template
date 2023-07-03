FROM alpine:latest

RUN apk update \ 
&& apk add openrc \
    php81 \
    php81-common \
    php81-session \
    php81-fpm \
    php81-pdo \
    php81-opcache \
    php81-zip \
    php81-phar \
    php81-iconv \
    php81-cli \
    php81-curl \
    php81-openssl \
    php81-mbstring \
    php81-tokenizer \
    php81-fileinfo \
    php81-json \
    php81-xml \
    php81-xmlwriter \
    php81-simplexml \
    php81-dom \
    php81-mysqli \    
    php81-pdo_mysql \
    php81-pdo_sqlite \
    php81-tokenizer \
    php81-gd \
    libmcrypt-dev \
    curl \
    libxml2-dev \
    apache2 \
    apache2-doc \
    apache2-utils

ENTRYPOINT httpd -k start && php-fpm81 -F -R