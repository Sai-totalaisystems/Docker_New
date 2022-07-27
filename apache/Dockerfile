FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update 
RUN apt-get install -y apache2  
RUN apt-get clean 
RUN apt-get install php7.4
RUN apt-get install mysql-server
RUN systemctl start mysql.service


ENV APACHE_LOG_DIR /var/log/apache2


ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
