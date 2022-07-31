FROM ubuntu:20.04
WORKDIR app/
COPY . ./

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update 
RUN apt-get install -y apache2  
RUN apt-get clean 
RUN apt-get install php7.4 -y
RUN apt-get install mysql-server -y
RUN apt-get install php-mysql -y
RUN service mysql start
COPY * ./var/www/php
ENV APACHE_LOG_DIR /var/log/apache2


#ENTRYPOINT ["/usr/sbin/apache2ctl","-D", "FOREGROUND"]
ENTRYPOINT ["/var/www/php","-D", "FOREGROUND"]
