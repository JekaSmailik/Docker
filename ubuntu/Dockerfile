#1шаг. Исходный образ из hab.docker.com
FROM ubuntu

#2шаг. Указал автора докер файла
MAINTAINER jeka Smailik <89181813770@mail.ru>

#3шаг. Обновил пакеты 
RUN apt update && apt upgrade -y 

#4шаг. Установка PHP7.4 (c fpm устанавливет nginx)
RUN apt install php7.4-fpm -y

#4шаг. Для утсановки php8. нужно 
#RUN apt install software-properties-common -y
#RUN add-apt-repository ppa:ondrej/php -y
#RUN apt update -y 
#RUN apt install php8.0 libapache2-mod-php8.0 -y

#5шаг. Установка пакетов gd, zip, xml и mbstring
RUN apt install php-gd php-zip php-xml php-mbstring -y

#6шаг. Обновил пакеты 
RUN apt update -y

#7шаг. Проверка версии PHP
RUN php -v

#8шаг. установил nginx
RUN apt install nginx -y

#9шаг. установил curl для caddy
RUN apt install curl -y 

#10-12шаг.
RUN apt install -y debian-keyring debian-archive-keyring apt-transport-https
RUN curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | apt-key add -
RUN curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | tee /etc/apt/sources.list.d/caddy-stable.list

#13шаг. установил caddy
RUN apt update && apt install caddy -y 

#14-18шаг. установка nginx-unit
RUN curl -sL https://nginx.org/keys/nginx_signing.key | apt-key add -
RUN echo "deb https://packages.nginx.org/unit/debian/ buster unit" > /etc/apt/sources.list.d/unit.list
RUN echo "deb-src https://packages.nginx.org/unit/debian/ buster unit" >> /etc/apt/sources.list.d/unit.list
RUN apt update -y
# Смотря для чего нужен Unit
#RUN apt install unit-dev unit-go unit-jsc11 unit-perl unit-php unit-python2.7 unit-python3.7 unit-ruby
RUN apt install unit -y 
