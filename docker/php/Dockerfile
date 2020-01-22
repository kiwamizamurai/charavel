FROM php:7.2-fpm-alpine
MAINTAINER kiwamizamurai

ARG TZ

RUN apk update && \
    docker-php-ext-install pdo_mysql


# If set to 1, this env disables the warning about running commands as root/super user.
# It also disables automatic clearing of sudo sessions, so you should really only set this
# if you use Composer as super user at all times like in docker containers.
# https://getcomposer.org/doc/03-cli.md#composer-allow-superuser
# ENV COMPOSER_ALLOW_SUPERUSER 1
# The COMPOSER_HOME var allows you to change the Composer home directory.
# This is a hidden, global (per-user on the machine) directory that is shared between all projects.
# ENV COMPOSER_HOME /composer
# ENV PATH $PATH:/composer/vendor/bin

# RUN set -eux && \
#     # https://qiita.com/pottava/items/970d7b5cda565b995fe7
#     # [.build-dependencies] is a set of all packages
#     # For example,
#     # apk del [.build-dependencies]
#   apk add --update-cache --no-cache --virtual=.build-dependencies tzdata && \
#     # Lets say Linux, timezone is located in /etc/localtime, but it is symbolic
#     # actual location is /usr/share/zoneinfo, but it is binary
#     # $ file /usr/share/zoneinfo/Japan
#     # /usr/share/zoneinfo/Japan: timezone data, version 2, 3 gmt time flags, 3 std time flags, no leap seconds, 8 transition times, 3 abbreviation chars
#     # $ zdump -v /usr/share/zoneinfo/Japan | tail
#     # /usr/share/zoneinfo/Japan  Sat May  6 14:59:59 1950 UTC = Sat May  6 23:59:59 1950 JST isdst=0
#     # /usr/share/zoneinfo/Japan  Sat May  6 15:00:00 1950 UTC = Sun May  7 01:00:00 1950 JDT isdst=1
#     # /usr/share/zoneinfo/Japan  Sat Sep  9 14:59:59 1950 UTC = Sun Sep 10 00:59:59 1950 JDT isdst=1
#   cp /usr/share/zoneinfo/${TZ} /etc/localtime && \
#   apk del .build-dependencies && \
#     # docker-php-ext-install is a build-in command to install php extensions in docker
#     # [bcmatch] is mathematical function
#     # https://www.php.net/manual/en/book.bc.php
#     # [pdo_mysql] is a driver between mysql and php
#     # laravels needs bcmath and pdo_mysql
#   docker-php-ext-install bcmath pdo_mysql && \
#     # install composer
#   curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
#   composer global require "laravel/installer"
#     # accelerating composer
# #  composer config -g repos.packagist composer https://packagist.jp && \
# #  composer global require hirak/prestissimo
#
# # WORKDIR is equivalent to cd command
# WORKDIR /work
# # create laravel project
# RUN composer create-project laravel/laravel laravel
#
# WORKDIR ..
