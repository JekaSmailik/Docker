#1шаг. Исходный образ из hab.docker.com
FROM fedora:34

#2шаг. Автор докер файла
MAINTAINER jeka Smailik <89181813770@mail.ru>

#3шаг. Обновил пакеты
RUN dnf update -y

#4шаг. Установка REMI 
RUN dnf install https://rpms.remirepo.net/fedora/remi-release-34.rpm -y

#5шаг. Дополнительные пакеты для PHP
RUN dnf module reset php -y

#6шаг. Установка PHP
RUN dnf module install php:remi-8.0 -y

#7шаг. Установка пакетов gd, zip, xml и mbstring
RUN dnf install php-gd php-zip php-xml php-mbstring -y

#8шаг. Обновить устаревшие пакеты
RUN dnf update -y

#9шаг. Проверка версии PHPv
RUN php -v

#10шаг. Установка nginx
RUN dnf install nginx -y

#11шаг. Установка caddy
RUN dnf install caddy -y

#12шаг. Установка unit-nginx
RUN echo "[unit]" > /etc/yum.repos.d/unit.repo
RUN echo "name=unit repo" >> /etc/yum.repos.d/unit.repo
RUN echo "baseurl=https://packages.nginx.org/unit/fedora/34/x86_64/" >> /etc/yum.repos.d/unit.repo
RUN echo "gpgcheck=0" >> /etc/yum.repos.d/unit.repo
RUN echo "enabled=1" >> /etc/yum.repos.d/unit.repo

#17шаг. 
RUN dnf update -y 
# Проверка файла RUN cat /etc/yum.repos.d/unit.repo

#18шаг. Смотря для чего нужен unit: install unit-devel unit-go unit-jsc11 unit-jsc8 unit-perl unit-php unit-python39 unit-ruby
RUN dnf install unit -y
