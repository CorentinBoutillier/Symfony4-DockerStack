FROM php:7.2-fpm-alpine

RUN apk update \
    && apk add bash git openssh ca-certificates wget freetype libpng libjpeg-turbo freetype-dev libpng-dev libjpeg-turbo-dev postgresql-dev zip libxml2-dev \
    && docker-php-ext-install gd pdo pdo_mysql pdo_pgsql zip pgsql xml soap \
    && rm /var/cache/apk/*

COPY init.sh /
RUN chmod +x /init.sh
CMD /init.sh
