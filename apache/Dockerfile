FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update 
RUN apt-get install -y apache2  
RUN apt-get clean && 
RUN apt-get install php7.4
RUN docker-php-ext-install mysqli


ENV APACHE_LOG_DIR /var/log/apache2


ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
