FROM ubuntu:18.04
RUN apt update && \
    ln -fs /usr/share/zoneinfo/Asia/Singapore /etc/localtime && \
    DEBIAN_FRONTEND=noninteractive apt install -y tzdata && \
    dpkg-reconfigure --frontend noninteractive tzdata && \
    apt purge libapache2-mod-php7.2 libapache2-mod-php && \
    DEBIAN_FRONTEND=noninteractive apt install -y php-mbstring curl vim  php php7.2-gd git libapache2-mod-php7.2 libapache2-mod-php apache2 && \
    a2dismod mpm_event && \
    a2enmod mpm_prefork && \
    a2enmod php7.2 && \
    git clone https://github.com/jax79sg/KODExplorer.git && \
    chmod -Rf 777 ./KODExplorer/* && \
    cd KODExplorer && \
    rm /var/www/html/index.html && \
    mv * /var/www/html/


EXPOSE 80
CMD apachectl -D FOREGROUND
