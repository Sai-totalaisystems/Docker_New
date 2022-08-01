#stage 1

FROM ubuntu:20.04
WORKDIR /

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install -y apache2
RUN apt-get clean
RUN apt-get install php7.4 -y
RUN apt-get install mysql-server -y
RUN apt-get install php-mysql -y
RUN --name some-mysql --restart unless-stopped -e MYSQL_ALLOW_EMPTY_PASSWORD=1 -p 3306:3306 -d mysql:latest
#RUN service mysql start

#RUN systemctl start mysql

#COPY . /var/www/


#RUN mkdir /var/www/php
#COPY /app/config/config.php ./var/www/php
#COPY /app/config/config.php ./var/www/
ENV APACHE_LOG_DIR /var/log/apache2

ENTRYPOINT ["/usr/sbin/apache2ctl","-D", "FOREGROUND"]
#ENTRYPOINT ["/var/www/php","-D", "FOREGROUND"]
#stage 3
#FROM mysql:8.0
