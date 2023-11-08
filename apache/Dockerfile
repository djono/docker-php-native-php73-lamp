FROM httpd:2.4.35-alpine
RUN apk update; \
    apk upgrade;
COPY ./apache.conf /usr/local/apache2/conf/httpd.conf
EXPOSE 8080
EXPOSE 8181
