FROM php:7.4-fpm-alpine3.16

ARG PUID=1000
ARG PGID=1000

RUN delgroup dialout 2> /dev/null || true;

RUN apk --no-cache add shadow; \
        usermod -u ${PUID} www-data; \
        groupmod -g ${PGID} www-data; \
        apk del shadow;

RUN chown ${PUID}:${PGID} -R /var/www/html

USER www-data

VOLUME /var/www/html/fileadmin
VOLUME /var/www/html/typo3_src
VOLUME /var/www/html/typo3conf
VOLUME /var/www/html/uploads

RUN ln -s /var/www/html/typo3_src/index.php /var/www/html/index.php

