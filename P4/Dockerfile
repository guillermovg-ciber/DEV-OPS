
#Version Debian

FROM debian

#Instalamos apache y php
RUN  apt-get update &&  apt-get install -y -qq apache2 php7.3
RUN  apt install libapache2-mod-evasive -y

#Directorios del servidor apache

WORKDIR /var/www/html

COPY . /var/www/html

COPY evasive.conf /etc/apache2/mods-enabled/

#Habilitamos el modulo php

RUN a2enmod php7.3

#Creamos la carpeta para logs y le asignamos dueño

RUN mkdir /var/log/mod_evasive
RUN chown -R root:www-data /var/log/mod_evasive
#Stat

#Por ultimo reiniciamos el servicio apache
RUN service apache2 restart
CMD ["./stat.sh"]
