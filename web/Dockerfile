FROM nginx:stable-alpine3.17

ARG PUID=1000
ARG PGID=1000

RUN apk --no-cache add shadow; \
        usermod -u ${PUID} nginx; \
        groupmod -g ${PGID} nginx; \
        apk del shadow;

VOLUME /var/www/html/fileadmin
VOLUME /var/www/html/typo3_src
VOLUME /var/www/html/typo3conf
VOLUME /var/www/html/uploads

RUN ln -s /var/www/html/typo3_src/index.php /var/www/html/index.php