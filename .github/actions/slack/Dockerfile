FROM composer:2.1.5 AS BUILDER

COPY composer.json \
     composer.lock \
     /app/

RUN composer install

FROM php:7.4.2

WORKDIR /app

COPY script.php .
COPY --from=BUILDER /app/ .

ENTRYPOINT ["php", "/app/script.php"]
