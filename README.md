Привіт, ДЗ з запізненнями, але моє , та від душі  )) 
в docker-compouser  два WEB додатка , обоє засусткаються , та працюють ) 
файли витягуються з docke hub , змого (відкритого) репозиторія  https://hub.docker.com/repositories/seventist 


docker-file 1 
# Використовуємо офіційний базовий образ PHP
FROM php:7.4-apache

# Встановлюємо додаткові розширення PHP, які вам потрібні
RUN docker-php-ext-install mysqli pdo_mysql

# Встановлюємо Composer (засіб для управління залежностями PHP)
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Копіюємо файли додатку в контейнер
COPY . /var/www/html/

# Необов'язково: Налаштовуємо Apache, наприклад, для включення модуля rewrite
RUN a2enmod rewrite

Docker-file 2 
FROM mongo:latest
RUN apt-get update &&  apt-get install -y
