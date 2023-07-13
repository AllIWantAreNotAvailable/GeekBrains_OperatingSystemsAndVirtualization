# Задача №1

> Установить Nginx

```bash
root@ubunto:~# sudo apt install nginx

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

The following additional packages will be installed:

  fontconfig-config fonts-dejavu-core libdeflate0 libfontconfig1 libgd3 libjbig0 libjpeg-turbo8 libjpeg8

  libnginx-mod-http-geoip2 libnginx-mod-http-image-filter libnginx-mod-http-xslt-filter libnginx-mod-mail

  libnginx-mod-stream libnginx-mod-stream-geoip2 libtiff5 libwebp7 libxpm4 nginx-common nginx-core

Suggested packages:

  libgd-tools fcgiwrap nginx-doc ssl-cert

The following NEW packages will be installed:

  fontconfig-config fonts-dejavu-core libdeflate0 libfontconfig1 libgd3 libjbig0 libjpeg-turbo8 libjpeg8

  libnginx-mod-http-geoip2 libnginx-mod-http-image-filter libnginx-mod-http-xslt-filter libnginx-mod-mail

  libnginx-mod-stream libnginx-mod-stream-geoip2 libtiff5 libwebp7 libxpm4 nginx nginx-common nginx-core

0 upgraded, 20 newly installed, 0 to remove and 1 not upgraded.

Need to get 2690 kB of archives.

After this operation, 8335 kB of additional disk space will be used.

Do you want to continue? [Y/n] y

Get:1 http://archive.ubuntu.com/ubuntu jammy/main amd64 fonts-dejavu-core all 2.37-2build1 [1041 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy/main amd64 fontconfig-config all 2.13.1-4.2ubuntu5 [29.1 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy/main amd64 libdeflate0 amd64 1.10-2 [70.9 kB]

Get:4 http://archive.ubuntu.com/ubuntu jammy/main amd64 libfontconfig1 amd64 2.13.1-4.2ubuntu5 [131 kB]

Get:5 http://archive.ubuntu.com/ubuntu jammy/main amd64 libjpeg-turbo8 amd64 2.1.2-0ubuntu1 [134 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy/main amd64 libjpeg8 amd64 8c-2ubuntu10 [2264 B]

Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libjbig0 amd64 2.1-3.1ubuntu0.22.04.1 [29.2 kB]

Get:8 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libwebp7 amd64 1.2.2-2ubuntu0.22.04.1 [206 kB]

Get:9 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libtiff5 amd64 4.3.0-6ubuntu0.4 [183 kB]

Get:10 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libxpm4 amd64 1:3.5.12-1ubuntu0.22.04.1 [36.4 kB]

Get:11 http://archive.ubuntu.com/ubuntu jammy/main amd64 libgd3 amd64 2.3.0-2ubuntu2 [129 kB]

Get:12 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx-common all 1.18.0-6ubuntu14.4 [40.0 kB]

Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-geoip2 amd64 1.18.0-6ubuntu14.4 [11.9 kB]

Get:14 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-image-filter amd64 1.18.0-6ubuntu14.4 [15.4 kB]

Get:15 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-xslt-filter amd64 1.18.0-6ubuntu14.4 [13.7 kB]

Get:16 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-mail amd64 1.18.0-6ubuntu14.4 [45.7 kB]

Get:17 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-stream amd64 1.18.0-6ubuntu14.4 [72.9 kB]

Get:18 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-stream-geoip2 amd64 1.18.0-6ubuntu14.4 [10.1 kB]

Get:19 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx-core amd64 1.18.0-6ubuntu14.4 [484 kB]

Get:20 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx amd64 1.18.0-6ubuntu14.4 [3872 B]

Fetched 2690 kB in 3s (897 kB/s)

Preconfiguring packages ...

Selecting previously unselected package fonts-dejavu-core.

(Reading database ... 64694 files and directories currently installed.)

Preparing to unpack .../00-fonts-dejavu-core_2.37-2build1_all.deb ...

Unpacking fonts-dejavu-core (2.37-2build1) ...

Selecting previously unselected package fontconfig-config.

Preparing to unpack .../01-fontconfig-config_2.13.1-4.2ubuntu5_all.deb ...

Unpacking fontconfig-config (2.13.1-4.2ubuntu5) ...

Selecting previously unselected package libdeflate0:amd64.

Preparing to unpack .../02-libdeflate0_1.10-2_amd64.deb ...

Unpacking libdeflate0:amd64 (1.10-2) ...

Selecting previously unselected package libfontconfig1:amd64.

Preparing to unpack .../03-libfontconfig1_2.13.1-4.2ubuntu5_amd64.deb ...

Unpacking libfontconfig1:amd64 (2.13.1-4.2ubuntu5) ...

Selecting previously unselected package libjpeg-turbo8:amd64.

Preparing to unpack .../04-libjpeg-turbo8_2.1.2-0ubuntu1_amd64.deb ...

Unpacking libjpeg-turbo8:amd64 (2.1.2-0ubuntu1) ...

Selecting previously unselected package libjpeg8:amd64.

Preparing to unpack .../05-libjpeg8_8c-2ubuntu10_amd64.deb ...

Unpacking libjpeg8:amd64 (8c-2ubuntu10) ...

Selecting previously unselected package libjbig0:amd64.

Preparing to unpack .../06-libjbig0_2.1-3.1ubuntu0.22.04.1_amd64.deb ...

Unpacking libjbig0:amd64 (2.1-3.1ubuntu0.22.04.1) ...

Selecting previously unselected package libwebp7:amd64.

Preparing to unpack .../07-libwebp7_1.2.2-2ubuntu0.22.04.1_amd64.deb ...

Unpacking libwebp7:amd64 (1.2.2-2ubuntu0.22.04.1) ...

Selecting previously unselected package libtiff5:amd64.

Preparing to unpack .../08-libtiff5_4.3.0-6ubuntu0.4_amd64.deb ...

Unpacking libtiff5:amd64 (4.3.0-6ubuntu0.4) ...

Selecting previously unselected package libxpm4:amd64.

Preparing to unpack .../09-libxpm4_1%3a3.5.12-1ubuntu0.22.04.1_amd64.deb ...

Unpacking libxpm4:amd64 (1:3.5.12-1ubuntu0.22.04.1) ...

Selecting previously unselected package libgd3:amd64.

Preparing to unpack .../10-libgd3_2.3.0-2ubuntu2_amd64.deb ...

Unpacking libgd3:amd64 (2.3.0-2ubuntu2) ...

Selecting previously unselected package nginx-common.

Preparing to unpack .../11-nginx-common_1.18.0-6ubuntu14.4_all.deb ...

Unpacking nginx-common (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-geoip2.

Preparing to unpack .../12-libnginx-mod-http-geoip2_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-geoip2 (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-image-filter.

Preparing to unpack .../13-libnginx-mod-http-image-filter_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-image-filter (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-xslt-filter.

Preparing to unpack .../14-libnginx-mod-http-xslt-filter_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-xslt-filter (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-mail.

Preparing to unpack .../15-libnginx-mod-mail_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-mail (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-stream.

Preparing to unpack .../16-libnginx-mod-stream_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-stream (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-stream-geoip2.

Preparing to unpack .../17-libnginx-mod-stream-geoip2_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-stream-geoip2 (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package nginx-core.

Preparing to unpack .../18-nginx-core_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking nginx-core (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package nginx.

Preparing to unpack .../19-nginx_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking nginx (1.18.0-6ubuntu14.4) ...

Setting up libxpm4:amd64 (1:3.5.12-1ubuntu0.22.04.1) ...

Setting up libdeflate0:amd64 (1.10-2) ...

Setting up nginx-common (1.18.0-6ubuntu14.4) ...

Created symlink /etc/systemd/system/multi-user.target.wants/nginx.service → /lib/systemd/system/nginx.service.

Setting up libjbig0:amd64 (2.1-3.1ubuntu0.22.04.1) ...

Setting up libnginx-mod-http-xslt-filter (1.18.0-6ubuntu14.4) ...

Setting up fonts-dejavu-core (2.37-2build1) ...

Setting up libjpeg-turbo8:amd64 (2.1.2-0ubuntu1) ...

Setting up libwebp7:amd64 (1.2.2-2ubuntu0.22.04.1) ...

Setting up libnginx-mod-http-geoip2 (1.18.0-6ubuntu14.4) ...

Setting up libjpeg8:amd64 (8c-2ubuntu10) ...

Setting up libnginx-mod-mail (1.18.0-6ubuntu14.4) ...

Setting up fontconfig-config (2.13.1-4.2ubuntu5) ...

Setting up libnginx-mod-stream (1.18.0-6ubuntu14.4) ...

Setting up libtiff5:amd64 (4.3.0-6ubuntu0.4) ...

Setting up libfontconfig1:amd64 (2.13.1-4.2ubuntu5) ...

Setting up libnginx-mod-stream-geoip2 (1.18.0-6ubuntu14.4) ...

Setting up libgd3:amd64 (2.3.0-2ubuntu2) ...

Setting up libnginx-mod-http-image-filter (1.18.0-6ubuntu14.4) ...

Setting up nginx-core (1.18.0-6ubuntu14.4) ...

 * Upgrading binary nginx                                                                                       [ OK ] 

Setting up nginx (1.18.0-6ubuntu14.4) ...

Processing triggers for ufw (0.36.1-4build1) ...

Processing triggers for man-db (2.10.2-1) ...

Processing triggers for libc-bin (2.35-0ubuntu3.1) ...

Scanning processes...                                                                                                  

Scanning linux images...                                                                                               

  

Running kernel seems to be up-to-date.

  

No services need to be restarted.

  

No containers need to be restarted.

  

No user sessions are running outdated binaries.

  

No VM guests are running outdated hypervisor (qemu) binaries on this host.

root@ubunto:~#
```

# Задача №2 (\*)

> настроить Nginx на работу с PHP-FPM

```bash

```

# Задача №3

> Установить Apache

```bash
root@ubunto:~# sudo apt install apache2

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

The following additional packages will be installed:

  apache2-bin apache2-data apache2-utils libapr1 libaprutil1 libaprutil1-dbd-sqlite3

  libaprutil1-ldap liblua5.3-0 ssl-cert

Suggested packages:

  apache2-doc apache2-suexec-pristine | apache2-suexec-custom www-browser

The following NEW packages will be installed:

  apache2 apache2-bin apache2-data apache2-utils libapr1 libaprutil1 libaprutil1-dbd-sqlite3

  libaprutil1-ldap liblua5.3-0 ssl-cert

0 upgraded, 10 newly installed, 0 to remove and 17 not upgraded.

Need to get 2075 kB of archives.

After this operation, 8281 kB of additional disk space will be used.

Do you want to continue? [Y/n] y

Get:1 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libapr1 amd64 1.7.0-8ubuntu0.22.04.1 [108 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libaprutil1 amd64 1.6.1-5ubuntu4.22.04.1 [92.6 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libaprutil1-dbd-sqlite3 amd64 1.6.1-5ubuntu4.22.04.1 [11.3 kB]

Get:4 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libaprutil1-ldap amd64 1.6.1-5ubuntu4.22.04.1 [9168 B]

Get:5 http://archive.ubuntu.com/ubuntu jammy/main amd64 liblua5.3-0 amd64 5.3.6-1build1 [140 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 apache2-bin amd64 2.4.52-1ubuntu4.5 [1345 kB]

Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 apache2-data all 2.4.52-1ubuntu4.5 [165 kB]

Get:8 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 apache2-utils amd64 2.4.52-1ubuntu4.5 [89.1 kB]

Get:9 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 apache2 amd64 2.4.52-1ubuntu4.5 [97.8 kB]

Get:10 http://archive.ubuntu.com/ubuntu jammy/main amd64 ssl-cert all 1.1.2 [17.4 kB]

Fetched 2075 kB in 1s (1636 kB/s)

Preconfiguring packages ...

Selecting previously unselected package libapr1:amd64.

(Reading database ... 66790 files and directories currently installed.)

Preparing to unpack .../0-libapr1_1.7.0-8ubuntu0.22.04.1_amd64.deb ...

Unpacking libapr1:amd64 (1.7.0-8ubuntu0.22.04.1) ...

Selecting previously unselected package libaprutil1:amd64.

Preparing to unpack .../1-libaprutil1_1.6.1-5ubuntu4.22.04.1_amd64.deb ...

Unpacking libaprutil1:amd64 (1.6.1-5ubuntu4.22.04.1) ...

Selecting previously unselected package libaprutil1-dbd-sqlite3:amd64.

Preparing to unpack .../2-libaprutil1-dbd-sqlite3_1.6.1-5ubuntu4.22.04.1_amd64.deb ...

Unpacking libaprutil1-dbd-sqlite3:amd64 (1.6.1-5ubuntu4.22.04.1) ...

Selecting previously unselected package libaprutil1-ldap:amd64.

Preparing to unpack .../3-libaprutil1-ldap_1.6.1-5ubuntu4.22.04.1_amd64.deb ...

Unpacking libaprutil1-ldap:amd64 (1.6.1-5ubuntu4.22.04.1) ...

Selecting previously unselected package liblua5.3-0:amd64.

Preparing to unpack .../4-liblua5.3-0_5.3.6-1build1_amd64.deb ...

Unpacking liblua5.3-0:amd64 (5.3.6-1build1) ...

Selecting previously unselected package apache2-bin.

Preparing to unpack .../5-apache2-bin_2.4.52-1ubuntu4.5_amd64.deb ...

Unpacking apache2-bin (2.4.52-1ubuntu4.5) ...

Selecting previously unselected package apache2-data.

Preparing to unpack .../6-apache2-data_2.4.52-1ubuntu4.5_all.deb ...

Unpacking apache2-data (2.4.52-1ubuntu4.5) ...

Selecting previously unselected package apache2-utils.

Preparing to unpack .../7-apache2-utils_2.4.52-1ubuntu4.5_amd64.deb ...

Unpacking apache2-utils (2.4.52-1ubuntu4.5) ...

Selecting previously unselected package apache2.

Preparing to unpack .../8-apache2_2.4.52-1ubuntu4.5_amd64.deb ...

Unpacking apache2 (2.4.52-1ubuntu4.5) ...

Selecting previously unselected package ssl-cert.

Preparing to unpack .../9-ssl-cert_1.1.2_all.deb ...

Unpacking ssl-cert (1.1.2) ...

Setting up libapr1:amd64 (1.7.0-8ubuntu0.22.04.1) ...

Setting up ssl-cert (1.1.2) ...

Setting up liblua5.3-0:amd64 (5.3.6-1build1) ...

Setting up apache2-data (2.4.52-1ubuntu4.5) ...

Setting up libaprutil1:amd64 (1.6.1-5ubuntu4.22.04.1) ...

Setting up libaprutil1-ldap:amd64 (1.6.1-5ubuntu4.22.04.1) ...

Setting up libaprutil1-dbd-sqlite3:amd64 (1.6.1-5ubuntu4.22.04.1) ...

Setting up apache2-utils (2.4.52-1ubuntu4.5) ...

Setting up apache2-bin (2.4.52-1ubuntu4.5) ...

Setting up apache2 (2.4.52-1ubuntu4.5) ...

Enabling module mpm_event.

Enabling module authz_core.

Enabling module authz_host.

Enabling module authn_core.

Enabling module auth_basic.

Enabling module access_compat.

Enabling module authn_file.

Enabling module authz_user.

Enabling module alias.

Enabling module dir.

Enabling module autoindex.

Enabling module env.

Enabling module mime.

Enabling module negotiation.

Enabling module setenvif.

Enabling module filter.

Enabling module deflate.

Enabling module status.

Enabling module reqtimeout.

Enabling conf charset.

Enabling conf localized-error-pages.

Enabling conf other-vhosts-access-log.

Enabling conf security.

Enabling conf serve-cgi-bin.

Enabling site 000-default.

Created symlink /etc/systemd/system/multi-user.target.wants/apache2.service → /lib/systemd/system/apache2.service.

Could not execute systemctl:  at /usr/bin/deb-systemd-invoke line 142.

Created symlink /etc/systemd/system/multi-user.target.wants/apache-htcacheclean.service → /lib/systemd/system/apache-htcacheclean.service.

Processing triggers for ufw (0.36.1-4build1) ...

Processing triggers for man-db (2.10.2-1) ...

Processing triggers for libc-bin (2.35-0ubuntu3.1) ...

Scanning processes...                                                                               

Scanning linux images...                                                                            

  

Running kernel seems to be up-to-date.

  

No services need to be restarted.

  

No containers need to be restarted.

  

No user sessions are running outdated binaries.

  

No VM guests are running outdated hypervisor (qemu) binaries on this host.

root@ubunto:~#
```

# Задача №4 (\*)

> Настроить обработку PHP. Добиться одновременной работы с Nginx

```bash

```

# Задача №5

> Настроить схему обратного прокси для Nginx (динамика - на Apache)

```bash
root@ubunto:~# cd /etc/nginx/

root@ubunto:/etc/nginx# ls -al

total 72

drwxr-xr-x  8 root root 4096 Jul 13 23:32 **.**

drwxr-xr-x 95 root root 4096 Jul 13 23:37 **..**

drwxr-xr-x  2 root root 4096 May 30 20:31 **conf.d**

-rw-r--r--  1 root root 1125 May 30 20:31 fastcgi.conf

-rw-r--r--  1 root root 1055 May 30 20:31 fastcgi_params

-rw-r--r--  1 root root 2837 May 30 20:31 koi-utf

-rw-r--r--  1 root root 2223 May 30 20:31 koi-win

-rw-r--r--  1 root root 3957 May 30 20:31 mime.types

drwxr-xr-x  2 root root 4096 May 30 20:31 **modules-available**

drwxr-xr-x  2 root root 4096 Jul 13 23:32 **modules-enabled**

-rw-r--r--  1 root root 1447 May 30 20:31 nginx.conf

-rw-r--r--  1 root root  180 May 30 20:31 proxy_params

-rw-r--r--  1 root root  636 May 30 20:31 scgi_params

drwxr-xr-x  2 root root 4096 Jul 13 23:32 **sites-available**

drwxr-xr-x  2 root root 4096 Jul 13 23:32 **sites-enabled**

drwxr-xr-x  2 root root 4096 Jul 13 23:32 **snippets**

-rw-r--r--  1 root root  664 May 30 20:31 uwsgi_params

-rw-r--r--  1 root root 3071 May 30 20:31 win-utf

root@ubunto:/etc/nginx# cd sites-enabled/

root@ubunto:/etc/nginx/sites-enabled# ls -al

total 8

drwxr-xr-x 2 root root 4096 Jul 13 23:32 **.**

drwxr-xr-x 8 root root 4096 Jul 13 23:42 **..**

lrwxrwxrwx 1 root root   34 Jul 13 23:32 **default** -> /etc/nginx/sites-available/default

root@ubunto:/etc/nginx/sites-enabled# vim default 

root@ubunto:/etc/nginx/sites-enabled# cat default

##

# You should look at the following URL's in order to grasp a solid understanding

# of Nginx configuration files in order to fully unleash the power of Nginx.

# https://www.nginx.com/resources/wiki/start/

# https://www.nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls/

# https://wiki.debian.org/Nginx/DirectoryStructure

#

# In most cases, administrators will remove this file from sites-enabled/ and

# leave it as reference inside of sites-available where it will continue to be

# updated by the nginx packaging team.

#

# This file will automatically load configuration files provided by other

# applications, such as Drupal or Wordpress. These applications will be made

# available underneath a path with that package name, such as /drupal8.

#

# Please see /usr/share/doc/nginx-doc/examples/ for more detailed examples.

##

  

# Default server configuration

#

server {

listen 80 default_server;

listen [::]:80 default_server;

  

# SSL configuration

#

# listen 443 ssl default_server;

# listen [::]:443 ssl default_server;

#

# Note: You should disable gzip for SSL traffic.

# See: https://bugs.debian.org/773332

#

# Read up on ssl_ciphers to ensure a secure configuration.

# See: https://bugs.debian.org/765782

#

# Self signed certs generated by the ssl-cert package

# Don't use them in a production server!

#

# include snippets/snakeoil.conf;

  

root /var/www/html;

  

# Add index.php to the list if you are using PHP

index index.html index.htm index.nginx-debian.html;

  

server_name _;

  

location / {

# First attempt to serve request as file, then

# as directory, then fall back to displaying a 404.

try_files $uri $uri/ =404;

}

  

# pass PHP scripts to FastCGI server

#

#location ~ \.php$ {

# include snippets/fastcgi-php.conf;

#

# # With php-fpm (or other unix sockets):

# fastcgi_pass unix:/run/php/php7.4-fpm.sock;

# # With php-cgi (or other tcp sockets):

# fastcgi_pass 127.0.0.1:9000;

#}

  

# deny access to .htaccess files, if Apache's document root

# concurs with nginx's one

#

#location ~ /\.ht {

# deny all;

#}

  

location / {

      proxy_pass http://localhost:8080;

    proxy_set_header Host $host;

    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    proxy_set_header X-Real-IP $remote_addr;

}

location ~* ^.+.(jpg|jpeg|gif|png|ico|css|zip|pdf|txt|tar|js)$ {

    root /var/www/html;

}

}

  

  

# Virtual Host configuration for example.com

#

# You can move that to a different file under sites-available/ and symlink that

# to sites-enabled/ to enable it.

#

#server {

# listen 80;

# listen [::]:80;

#

# server_name example.com;

#

# root /var/www/example.com;

# index index.html;

#

# location / {

# try_files $uri $uri/ =404;

# }

#}

root@ubunto:/etc/nginx/sites-enabled#
```

# Задача №6

> Установить MySQL. Создать новую базу данных и таблицу в ней

```bash
root@ubunto:/etc/nginx# sudo apt install mysql-server mysql-client

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

The following additional packages will be installed:

  libcgi-fast-perl libcgi-pm-perl libclone-perl libencode-locale-perl libevent-pthreads-2.1-7

  libfcgi-bin libfcgi-perl libfcgi0ldbl libhtml-parser-perl libhtml-tagset-perl

  libhtml-template-perl libhttp-date-perl libhttp-message-perl libio-html-perl

  liblwp-mediatypes-perl libmecab2 libprotobuf-lite23 libtimedate-perl liburi-perl mecab-ipadic

  mecab-ipadic-utf8 mecab-utils mysql-client-8.0 mysql-client-core-8.0 mysql-common

  mysql-server-8.0 mysql-server-core-8.0

Suggested packages:

  libdata-dump-perl libipc-sharedcache-perl libbusiness-isbn-perl libwww-perl mailx tinyca

The following NEW packages will be installed:

  libcgi-fast-perl libcgi-pm-perl libclone-perl libencode-locale-perl libevent-pthreads-2.1-7

  libfcgi-bin libfcgi-perl libfcgi0ldbl libhtml-parser-perl libhtml-tagset-perl

  libhtml-template-perl libhttp-date-perl libhttp-message-perl libio-html-perl

  liblwp-mediatypes-perl libmecab2 libprotobuf-lite23 libtimedate-perl liburi-perl mecab-ipadic

  mecab-ipadic-utf8 mecab-utils mysql-client mysql-client-8.0 mysql-client-core-8.0 mysql-common

  mysql-server mysql-server-8.0 mysql-server-core-8.0

0 upgraded, 29 newly installed, 0 to remove and 0 not upgraded.

Need to get 29.6 MB of archives.

After this operation, 243 MB of additional disk space will be used.

Do you want to continue? [Y/n] y

Get:1 http://archive.ubuntu.com/ubuntu jammy/main amd64 mysql-common all 5.8+1.0.8 [7212 B]

Get:2 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 mysql-client-core-8.0 amd64 8.0.33-0ubuntu0.22.04.2 [2802 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 mysql-client-8.0 amd64 8.0.33-0ubuntu0.22.04.2 [22.7 kB]

Get:4 http://archive.ubuntu.com/ubuntu jammy/main amd64 libevent-pthreads-2.1-7 amd64 2.1.12-stable-1build3 [7642 B]

Get:5 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmecab2 amd64 0.996-14build9 [199 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libprotobuf-lite23 amd64 3.12.4-1ubuntu7.22.04.1 [209 kB]

Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 mysql-server-core-8.0 amd64 8.0.33-0ubuntu0.22.04.2 [17.5 MB]

Get:8 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 mysql-server-8.0 amd64 8.0.33-0ubuntu0.22.04.2 [1431 kB]

Get:9 http://archive.ubuntu.com/ubuntu jammy/main amd64 libhtml-tagset-perl all 3.20-4 [12.5 kB]

Get:10 http://archive.ubuntu.com/ubuntu jammy/main amd64 liburi-perl all 5.10-1 [78.8 kB]

Get:11 http://archive.ubuntu.com/ubuntu jammy/main amd64 libhtml-parser-perl amd64 3.76-1build2 [88.4 kB]

Get:12 http://archive.ubuntu.com/ubuntu jammy/main amd64 libcgi-pm-perl all 4.54-1 [188 kB]

Get:13 http://archive.ubuntu.com/ubuntu jammy/main amd64 libfcgi0ldbl amd64 2.4.2-2build2 [28.0 kB]

Get:14 http://archive.ubuntu.com/ubuntu jammy/main amd64 libfcgi-perl amd64 0.82+ds-1build1 [22.8 kB]

Get:15 http://archive.ubuntu.com/ubuntu jammy/main amd64 libcgi-fast-perl all 1:2.15-1 [10.5 kB]

Get:16 http://archive.ubuntu.com/ubuntu jammy/main amd64 libclone-perl amd64 0.45-1build3 [11.0 kB]

Get:17 http://archive.ubuntu.com/ubuntu jammy/main amd64 libencode-locale-perl all 1.05-1.1 [11.8 kB]

Get:18 http://archive.ubuntu.com/ubuntu jammy/main amd64 libfcgi-bin amd64 2.4.2-2build2 [11.2 kB]

Get:19 http://archive.ubuntu.com/ubuntu jammy/main amd64 libhtml-template-perl all 2.97-1.1 [59.1 kB]

Get:20 http://archive.ubuntu.com/ubuntu jammy/main amd64 libtimedate-perl all 2.3300-2 [34.0 kB]

Get:21 http://archive.ubuntu.com/ubuntu jammy/main amd64 libhttp-date-perl all 6.05-1 [9920 B]

Get:22 http://archive.ubuntu.com/ubuntu jammy/main amd64 libio-html-perl all 1.004-2 [15.4 kB]

Get:23 http://archive.ubuntu.com/ubuntu jammy/main amd64 liblwp-mediatypes-perl all 6.04-1 [19.5 kB]

Get:24 http://archive.ubuntu.com/ubuntu jammy/main amd64 libhttp-message-perl all 6.36-1 [76.8 kB]  

Get:25 http://archive.ubuntu.com/ubuntu jammy/main amd64 mecab-utils amd64 0.996-14build9 [4850 B]  

Get:26 http://archive.ubuntu.com/ubuntu jammy/main amd64 mecab-ipadic all 2.7.0-20070801+main-3 [6718 kB]

Get:27 http://archive.ubuntu.com/ubuntu jammy/main amd64 mecab-ipadic-utf8 all 2.7.0-20070801+main-3 [4384 B]

Get:28 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 mysql-client all 8.0.33-0ubuntu0.22.04.2 [9358 B]

Get:29 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 mysql-server all 8.0.33-0ubuntu0.22.04.2 [9462 B]

Fetched 29.6 MB in 9s (3476 kB/s)                                                                   

Preconfiguring packages ...

Selecting previously unselected package mysql-common.

(Reading database ... 65651 files and directories currently installed.)

Preparing to unpack .../0-mysql-common_5.8+1.0.8_all.deb ...

Unpacking mysql-common (5.8+1.0.8) ...

Selecting previously unselected package mysql-client-core-8.0.

Preparing to unpack .../1-mysql-client-core-8.0_8.0.33-0ubuntu0.22.04.2_amd64.deb ...

Unpacking mysql-client-core-8.0 (8.0.33-0ubuntu0.22.04.2) ...

Selecting previously unselected package mysql-client-8.0.

Preparing to unpack .../2-mysql-client-8.0_8.0.33-0ubuntu0.22.04.2_amd64.deb ...

Unpacking mysql-client-8.0 (8.0.33-0ubuntu0.22.04.2) ...

Selecting previously unselected package libevent-pthreads-2.1-7:amd64.

Preparing to unpack .../3-libevent-pthreads-2.1-7_2.1.12-stable-1build3_amd64.deb ...

Unpacking libevent-pthreads-2.1-7:amd64 (2.1.12-stable-1build3) ...

Selecting previously unselected package libmecab2:amd64.

Preparing to unpack .../4-libmecab2_0.996-14build9_amd64.deb ...

Unpacking libmecab2:amd64 (0.996-14build9) ...

Selecting previously unselected package libprotobuf-lite23:amd64.

Preparing to unpack .../5-libprotobuf-lite23_3.12.4-1ubuntu7.22.04.1_amd64.deb ...

Unpacking libprotobuf-lite23:amd64 (3.12.4-1ubuntu7.22.04.1) ...

Selecting previously unselected package mysql-server-core-8.0.

Preparing to unpack .../6-mysql-server-core-8.0_8.0.33-0ubuntu0.22.04.2_amd64.deb ...

Unpacking mysql-server-core-8.0 (8.0.33-0ubuntu0.22.04.2) ...

Setting up mysql-common (5.8+1.0.8) ...

update-alternatives: using /etc/mysql/my.cnf.fallback to provide /etc/mysql/my.cnf (my.cnf) in auto mode

Selecting previously unselected package mysql-server-8.0.

(Reading database ... 65865 files and directories currently installed.)

Preparing to unpack .../00-mysql-server-8.0_8.0.33-0ubuntu0.22.04.2_amd64.deb ...

Unpacking mysql-server-8.0 (8.0.33-0ubuntu0.22.04.2) ...

Selecting previously unselected package libhtml-tagset-perl.

Preparing to unpack .../01-libhtml-tagset-perl_3.20-4_all.deb ...

Unpacking libhtml-tagset-perl (3.20-4) ...

Selecting previously unselected package liburi-perl.

Preparing to unpack .../02-liburi-perl_5.10-1_all.deb ...

Unpacking liburi-perl (5.10-1) ...

Selecting previously unselected package libhtml-parser-perl:amd64.

Preparing to unpack .../03-libhtml-parser-perl_3.76-1build2_amd64.deb ...

Unpacking libhtml-parser-perl:amd64 (3.76-1build2) ...

Selecting previously unselected package libcgi-pm-perl.

Preparing to unpack .../04-libcgi-pm-perl_4.54-1_all.deb ...

Unpacking libcgi-pm-perl (4.54-1) ...

Selecting previously unselected package libfcgi0ldbl:amd64.

Preparing to unpack .../05-libfcgi0ldbl_2.4.2-2build2_amd64.deb ...

Unpacking libfcgi0ldbl:amd64 (2.4.2-2build2) ...

Selecting previously unselected package libfcgi-perl:amd64.

Preparing to unpack .../06-libfcgi-perl_0.82+ds-1build1_amd64.deb ...

Unpacking libfcgi-perl:amd64 (0.82+ds-1build1) ...

Selecting previously unselected package libcgi-fast-perl.

Preparing to unpack .../07-libcgi-fast-perl_1%3a2.15-1_all.deb ...

Unpacking libcgi-fast-perl (1:2.15-1) ...

Selecting previously unselected package libclone-perl.

Preparing to unpack .../08-libclone-perl_0.45-1build3_amd64.deb ...

Unpacking libclone-perl (0.45-1build3) ...

Selecting previously unselected package libencode-locale-perl.

Preparing to unpack .../09-libencode-locale-perl_1.05-1.1_all.deb ...

Unpacking libencode-locale-perl (1.05-1.1) ...

Selecting previously unselected package libfcgi-bin.

Preparing to unpack .../10-libfcgi-bin_2.4.2-2build2_amd64.deb ...

Unpacking libfcgi-bin (2.4.2-2build2) ...

Selecting previously unselected package libhtml-template-perl.

Preparing to unpack .../11-libhtml-template-perl_2.97-1.1_all.deb ...

Unpacking libhtml-template-perl (2.97-1.1) ...

Selecting previously unselected package libtimedate-perl.

Preparing to unpack .../12-libtimedate-perl_2.3300-2_all.deb ...

Unpacking libtimedate-perl (2.3300-2) ...

Selecting previously unselected package libhttp-date-perl.

Preparing to unpack .../13-libhttp-date-perl_6.05-1_all.deb ...

Unpacking libhttp-date-perl (6.05-1) ...

Selecting previously unselected package libio-html-perl.

Preparing to unpack .../14-libio-html-perl_1.004-2_all.deb ...

Unpacking libio-html-perl (1.004-2) ...

Selecting previously unselected package liblwp-mediatypes-perl.

Preparing to unpack .../15-liblwp-mediatypes-perl_6.04-1_all.deb ...

Unpacking liblwp-mediatypes-perl (6.04-1) ...

Selecting previously unselected package libhttp-message-perl.

Preparing to unpack .../16-libhttp-message-perl_6.36-1_all.deb ...

Unpacking libhttp-message-perl (6.36-1) ...

Selecting previously unselected package mecab-utils.

Preparing to unpack .../17-mecab-utils_0.996-14build9_amd64.deb ...

Unpacking mecab-utils (0.996-14build9) ...

Selecting previously unselected package mecab-ipadic.

Preparing to unpack .../18-mecab-ipadic_2.7.0-20070801+main-3_all.deb ...

Unpacking mecab-ipadic (2.7.0-20070801+main-3) ...

Selecting previously unselected package mecab-ipadic-utf8.

Preparing to unpack .../19-mecab-ipadic-utf8_2.7.0-20070801+main-3_all.deb ...

Unpacking mecab-ipadic-utf8 (2.7.0-20070801+main-3) ...

Selecting previously unselected package mysql-client.

Preparing to unpack .../20-mysql-client_8.0.33-0ubuntu0.22.04.2_all.deb ...

Unpacking mysql-client (8.0.33-0ubuntu0.22.04.2) ...

Selecting previously unselected package mysql-server.

Preparing to unpack .../21-mysql-server_8.0.33-0ubuntu0.22.04.2_all.deb ...

Unpacking mysql-server (8.0.33-0ubuntu0.22.04.2) ...

Setting up libmecab2:amd64 (0.996-14build9) ...

Setting up mysql-client-core-8.0 (8.0.33-0ubuntu0.22.04.2) ...

Setting up libfcgi0ldbl:amd64 (2.4.2-2build2) ...

Setting up libclone-perl (0.45-1build3) ...

Setting up libhtml-tagset-perl (3.20-4) ...

Setting up liblwp-mediatypes-perl (6.04-1) ...

Setting up libfcgi-bin (2.4.2-2build2) ...

Setting up libencode-locale-perl (1.05-1.1) ...

Setting up libprotobuf-lite23:amd64 (3.12.4-1ubuntu7.22.04.1) ...

Setting up mecab-utils (0.996-14build9) ...

Setting up libio-html-perl (1.004-2) ...

Setting up libtimedate-perl (2.3300-2) ...

Setting up mysql-client-8.0 (8.0.33-0ubuntu0.22.04.2) ...

Setting up libfcgi-perl:amd64 (0.82+ds-1build1) ...

Setting up liburi-perl (5.10-1) ...

Setting up libevent-pthreads-2.1-7:amd64 (2.1.12-stable-1build3) ...

Setting up libhttp-date-perl (6.05-1) ...

Setting up mysql-client (8.0.33-0ubuntu0.22.04.2) ...

Setting up mecab-ipadic (2.7.0-20070801+main-3) ...

Compiling IPA dictionary for Mecab.  This takes long time...

reading /usr/share/mecab/dic/ipadic/unk.def ... 40

emitting double-array: 100% |###########################################| 

/usr/share/mecab/dic/ipadic/model.def is not found. skipped.

reading /usr/share/mecab/dic/ipadic/Noun.csv ... 60477

reading /usr/share/mecab/dic/ipadic/Suffix.csv ... 1393

reading /usr/share/mecab/dic/ipadic/Noun.others.csv ... 151

reading /usr/share/mecab/dic/ipadic/Noun.adjv.csv ... 3328

reading /usr/share/mecab/dic/ipadic/Postp.csv ... 146

reading /usr/share/mecab/dic/ipadic/Postp-col.csv ... 91

reading /usr/share/mecab/dic/ipadic/Filler.csv ... 19

reading /usr/share/mecab/dic/ipadic/Noun.number.csv ... 42

reading /usr/share/mecab/dic/ipadic/Noun.nai.csv ... 42

reading /usr/share/mecab/dic/ipadic/Noun.name.csv ... 34202

reading /usr/share/mecab/dic/ipadic/Noun.place.csv ... 72999

reading /usr/share/mecab/dic/ipadic/Noun.proper.csv ... 27328

reading /usr/share/mecab/dic/ipadic/Adnominal.csv ... 135

reading /usr/share/mecab/dic/ipadic/Noun.demonst.csv ... 120

reading /usr/share/mecab/dic/ipadic/Adverb.csv ... 3032

reading /usr/share/mecab/dic/ipadic/Auxil.csv ... 199

reading /usr/share/mecab/dic/ipadic/Conjunction.csv ... 171

reading /usr/share/mecab/dic/ipadic/Verb.csv ... 130750

reading /usr/share/mecab/dic/ipadic/Noun.org.csv ... 16668

reading /usr/share/mecab/dic/ipadic/Others.csv ... 2

reading /usr/share/mecab/dic/ipadic/Prefix.csv ... 221

reading /usr/share/mecab/dic/ipadic/Noun.verbal.csv ... 12146

reading /usr/share/mecab/dic/ipadic/Adj.csv ... 27210

reading /usr/share/mecab/dic/ipadic/Noun.adverbal.csv ... 795

reading /usr/share/mecab/dic/ipadic/Symbol.csv ... 208

reading /usr/share/mecab/dic/ipadic/Interjection.csv ... 252

emitting double-array: 100% |###########################################| 

reading /usr/share/mecab/dic/ipadic/matrix.def ... 1316x1316

emitting matrix      : 100% |###########################################| 

  

done!

update-alternatives: using /var/lib/mecab/dic/ipadic to provide /var/lib/mecab/dic/debian (mecab-dictionary) in auto mode

Setting up mysql-server-core-8.0 (8.0.33-0ubuntu0.22.04.2) ...

Setting up mecab-ipadic-utf8 (2.7.0-20070801+main-3) ...

Compiling IPA dictionary for Mecab.  This takes long time...

reading /usr/share/mecab/dic/ipadic/unk.def ... 40

emitting double-array: 100% |###########################################| 

/usr/share/mecab/dic/ipadic/model.def is not found. skipped.

reading /usr/share/mecab/dic/ipadic/Noun.csv ... 60477

reading /usr/share/mecab/dic/ipadic/Suffix.csv ... 1393

reading /usr/share/mecab/dic/ipadic/Noun.others.csv ... 151

reading /usr/share/mecab/dic/ipadic/Noun.adjv.csv ... 3328

reading /usr/share/mecab/dic/ipadic/Postp.csv ... 146

reading /usr/share/mecab/dic/ipadic/Postp-col.csv ... 91

reading /usr/share/mecab/dic/ipadic/Filler.csv ... 19

reading /usr/share/mecab/dic/ipadic/Noun.number.csv ... 42

reading /usr/share/mecab/dic/ipadic/Noun.nai.csv ... 42

reading /usr/share/mecab/dic/ipadic/Noun.name.csv ... 34202

reading /usr/share/mecab/dic/ipadic/Noun.place.csv ... 72999

reading /usr/share/mecab/dic/ipadic/Noun.proper.csv ... 27328

reading /usr/share/mecab/dic/ipadic/Adnominal.csv ... 135

reading /usr/share/mecab/dic/ipadic/Noun.demonst.csv ... 120

reading /usr/share/mecab/dic/ipadic/Adverb.csv ... 3032

reading /usr/share/mecab/dic/ipadic/Auxil.csv ... 199

reading /usr/share/mecab/dic/ipadic/Conjunction.csv ... 171

reading /usr/share/mecab/dic/ipadic/Verb.csv ... 130750

reading /usr/share/mecab/dic/ipadic/Noun.org.csv ... 16668

reading /usr/share/mecab/dic/ipadic/Others.csv ... 2

reading /usr/share/mecab/dic/ipadic/Prefix.csv ... 221

reading /usr/share/mecab/dic/ipadic/Noun.verbal.csv ... 12146

reading /usr/share/mecab/dic/ipadic/Adj.csv ... 27210

reading /usr/share/mecab/dic/ipadic/Noun.adverbal.csv ... 795

reading /usr/share/mecab/dic/ipadic/Symbol.csv ... 208

reading /usr/share/mecab/dic/ipadic/Interjection.csv ... 252

emitting double-array: 100% |###########################################| 

reading /usr/share/mecab/dic/ipadic/matrix.def ... 1316x1316

emitting matrix      : 100% |###########################################| 

  

done!

update-alternatives: using /var/lib/mecab/dic/ipadic-utf8 to provide /var/lib/mecab/dic/debian (mecab-dictionary) in auto mode

Setting up libhtml-parser-perl:amd64 (3.76-1build2) ...

Setting up libhttp-message-perl (6.36-1) ...

Setting up mysql-server-8.0 (8.0.33-0ubuntu0.22.04.2) ...

update-alternatives: using /etc/mysql/mysql.cnf to provide /etc/mysql/my.cnf (my.cnf) in auto mode

Renaming removed key_buffer and myisam-recover options (if present)

mysqld will log errors to /var/log/mysql/error.log

mysqld is running as pid 5199

Created symlink /etc/systemd/system/multi-user.target.wants/mysql.service → /lib/systemd/system/mysql.service.

Setting up libcgi-pm-perl (4.54-1) ...

Setting up libhtml-template-perl (2.97-1.1) ...

Setting up mysql-server (8.0.33-0ubuntu0.22.04.2) ...

Setting up libcgi-fast-perl (1:2.15-1) ...

Processing triggers for man-db (2.10.2-1) ...

Processing triggers for libc-bin (2.35-0ubuntu3.1) ...

Scanning processes...                                                                                

Scanning linux images...                                                                             

  

Running kernel seems to be up-to-date.

  

No services need to be restarted.

  

No containers need to be restarted.

  

No user sessions are running outdated binaries.

  

No VM guests are running outdated hypervisor (qemu) binaries on this host.

root@ubunto:/etc/nginx# sudo mysql

Welcome to the MySQL monitor.  Commands end with ; or \g.

Your MySQL connection id is 19

Server version: 8.0.33-0ubuntu0.22.04.2 (Ubuntu)

  

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

  

Oracle is a registered trademark of Oracle Corporation and/or its

affiliates. Other names may be trademarks of their respective

owners.

  

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

  

mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '1234567890';

Query OK, 0 rows affected (0.01 sec)

  

mysql> exit

Bye

root@ubunto:/etc/nginx# mysql_secure_installation

  

Securing the MySQL server deployment.

  

Enter password for user root: 

The 'validate_password' component is installed on the server.

The subsequent steps will run with the existing configuration

of the component.

Using existing password for root.

  

Estimated strength of the password: 50 

Change the password for root ? ((Press y|Y for Yes, any other key for No) : n

  

 ... skipping.

By default, a MySQL installation has an anonymous user,

allowing anyone to log into MySQL without having to have

a user account created for them. This is intended only for

testing, and to make the installation go a bit smoother.

You should remove them before moving into a production

environment.

  

Remove anonymous users? (Press y|Y for Yes, any other key for No) : y

Success.

  

  

Normally, root should only be allowed to connect from

'localhost'. This ensures that someone cannot guess at

the root password from the network.

  

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y

Success.

  

By default, MySQL comes with a database named 'test' that

anyone can access. This is also intended only for testing,

and should be removed before moving into a production

environment.

  

  

Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y

 - Dropping test database...

Success.

  

 - Removing privileges on test database...

Success.

  

Reloading the privilege tables will ensure that all changes

made so far will take effect immediately.

  

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y

Success.

  

All done! 


root@ubunto:~# sudo mysql -p

Enter password: 

Welcome to the MySQL monitor.  Commands end with ; or \g.

Your MySQL connection id is 27

Server version: 8.0.33-0ubuntu0.22.04.2 (Ubuntu)

  

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

  

Oracle is a registered trademark of Oracle Corporation and/or its

affiliates. Other names may be trademarks of their respective

owners.

  

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

  

mysql> CREATE DATABASE testdb;

Query OK, 1 row affected (0.00 sec)

  

mysql> USE testdb

Database changed

mysql> CREATE TABLE testtable (id INT);

Query OK, 0 rows affected (0.03 sec)

  

mysql> INSERT testtable (id) VALUES (1);

Query OK, 1 row affected (0.02 sec)

  

mysql> SELECT * FROM testtable;

+------+

| id   |

+------+

|    1 |

+------+

1 row in set (0.00 sec)

  

mysql> exit;

Bye

root@ubunto:~#
```

# Задача №7 (\*)

> Установить пакет phpmyadmin и запустить его веб-интерфейс для управления MySQL

```bash

```
