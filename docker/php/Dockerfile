# https://hub.docker.com/_/php?tab=tags
FROM php:8.3.15-cli-alpine

RUN apk add postgresql-dev
RUN docker-php-ext-install pdo_pgsql
RUN docker-php-ext-install pcntl

RUN apk add --no-cache --virtual .build-deps $PHPIZE_DEPS linux-headers

RUN curl -L -o /tmp/todo-ext.tar.gz https://github.com/gquemener/todo-ext/archive/refs/tags/0.1.0.tar.gz
RUN mkdir /tmp/todo-ext && \
    tar -xzvf /tmp/todo-ext.tar.gz -C /tmp/todo-ext --strip-components=1 && \
    cd /tmp/todo-ext &&\
    phpize && \
    ./configure && \
    make && \
    make install && \
    echo "extension=todo" > /usr/local/etc/php/conf.d/todo.ini

RUN pecl install xdebug
COPY xdebug.ini /usr/local/etc/php/conf.d/
RUN apk del .build-deps

# https://hub.docker.com/_/composer?tab=tags
COPY --from=composer:2.8.3 /usr/bin/composer /usr/bin/composer

CMD ["php", "-v"]
