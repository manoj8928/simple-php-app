# Pull base image.
FROM ubuntu:14.04

# Install following packages

RUN apt-get update && apt-get -y install curl php5-cli php5-common php5-mysql php5-xdebug libapache2-mod-php5 apache2 nano \
software-properties-common --force-yes -y

RUN add-apt-repository ppa:ondrej/php && apt-get update && apt-get install php5 curl php5-curl --force-yes -y
COPY app/ /var/www/html

# Replacing dir.conf
RUN rm -f /etc/apache2/mods-available/dir.conf
COPY dir.conf /etc/apache2/mods-available/

EXPOSE 80
CMD /usr/sbin/apache2ctl -D FOREGROUND
