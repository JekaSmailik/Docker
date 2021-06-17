#1 шаг. Исходный образ из hab.docker.com
FROM alpine

#2 шаг. Автор докер файла
MAINTAINER Jeka Smailik <89181813770@mail.ru>

#3 шаг. Обновил пакеты
RUN apk update && apk upgrade 

#4 шаг. Установка PHP 
RUN apk add php

#5 шаг. Проверка версии PHP
RUN php -v

#6 шаг. Установка пакетов gd, zip, xml и mbstring
RUN apk add php-gd php-zip php-xml php-mbstring

#7 шаг. Обновление пакетов
RUN apk update

#8 шаг. Установка nginx 
RUN apk add nginx

#9 шаг. Проверка версии nginx
RUN nginx -v

#10 шаг. Установка caddy 
RUN apk add caddy

