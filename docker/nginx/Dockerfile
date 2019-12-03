FROM alpine:3.10

LABEL maintainer="Chaabani Hammadi <chaabani.hammadi@gmail.com>"

RUN apk add --update --no-cache nginx

COPY nginx.conf /etc/nginx/
COPY symfony.conf /etc/nginx/conf.d/

RUN echo "upstream php-upstream { server php:9001; }" > /etc/nginx/conf.d/upstream.conf

RUN adduser -D -g '' -G www-data www-data

CMD ["nginx"]

RUN chown -R www-data /var/www
RUN chmod -R 777 /var/www

EXPOSE 80
EXPOSE 443
