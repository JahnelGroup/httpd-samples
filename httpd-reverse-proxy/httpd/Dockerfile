ARG APACHE_VERSION=""
FROM httpd:${APACHE_VERSION:+${APACHE_VERSION}-}alpine

RUN apk update; \
    apk upgrade;

COPY httpd.conf /usr/local/apache2/conf/httpd.conf
COPY httpd-proxy.conf /usr/local/apache2/conf/httpd-proxy.conf
