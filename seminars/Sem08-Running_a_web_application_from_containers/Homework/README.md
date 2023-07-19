# Задача №1 

> Переустановить операционную систему (по желанию, для дополнительной практики)

Пример переустановки linux VM в среде Canonical Multipass:

```bash
# 1. Create ssh-key
$ ssh-keygen -C vmuser -f multipass-ssh-key

# 2. Create cloud-init configuration
$ cat > cloud-init.yaml                                                       

users:

  - default

  - name: vmuser

    sudo: ALL=(ALL) NOPASSWD:ALL

    ssh_authorized_keys:

    - <content of public key>

# 3. Launch multipass VM with ssh configuration
$ multipass launch -n testvm --cloud-init cloud-init.yaml

# 4. Find IP address of new VM
$ multipass info testvm

Name:           testvm
State:          Running
IPv4:           192.168.64.6
Release:        Ubuntu 20.04.4 LTS
Image hash:     692406940d6a (Ubuntu 20.04 LTS)
Load:           0.00 0.00 0.00
Disk usage:     1.5G out of 4.7G
Memory usage:   140.5M out of 976.9M
Mounts:         --

# 5. ssh into new VM
$ ssh vmuser@192.168.64.6 -i multipass-ssh-key -o StrictHostKeyChecking=no
Enter passphrase for key 'multipass-ssh-key': 

Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.15.0-76-generic x86_64)

  

 * Documentation:  https://help.ubuntu.com

 * Management:     https://landscape.canonical.com

 * Support:        https://ubuntu.com/advantage

  

  System information as of Fri Jul 14 00:46:58 MSK 2023

  

  System load:           0.12353515625

  Usage of /:            46.0% of 4.67GB

  Memory usage:          59%

  Swap usage:            0%

  Processes:             95

  Users logged in:       0

  IPv4 address for ens3: 192.168.64.6

  IPv6 address for ens3: fd1c:5fe9:1ec1:257f:5054:ff:fe14:a8d3

  

  

Expanded Security Maintenance for Applications is not enabled.

  

0 updates can be applied immediately.

  

Enable ESM Apps to receive additional future security updates.

See https://ubuntu.com/esm or run: sudo pro status

  

  

Last login: Fri Jul 14 00:27:35 2023 from 192.168.64.1

root@ubunto:~#
```


# Задача №2

> Установить Docker.


```bash
root@ubunto:~# sudo apt install docker.io

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

The following additional packages will be installed:

  bridge-utils containerd dns-root-data dnsmasq-base pigz runc ubuntu-fan

Suggested packages:

  ifupdown aufs-tools cgroupfs-mount | cgroup-lite debootstrap docker-doc rinse zfs-fuse | zfsutils

The following NEW packages will be installed:

  bridge-utils containerd dns-root-data dnsmasq-base docker.io pigz runc ubuntu-fan

0 upgraded, 8 newly installed, 0 to remove and 0 not upgraded.

Need to get 72.4 MB of archives.

After this operation, 287 MB of additional disk space will be used.

Do you want to continue? [Y/n] y

Get:1 http://archive.ubuntu.com/ubuntu jammy/universe amd64 pigz amd64 2.6-1 [63.6 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy/main amd64 bridge-utils amd64 1.7-1ubuntu3 [34.4 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 runc amd64 1.1.4-0ubuntu1~22.04.3 [4244 kB]

Get:4 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 containerd amd64 1.6.12-0ubuntu1~22.04.3 [34.4 MB]

Get:5 http://archive.ubuntu.com/ubuntu jammy/main amd64 dns-root-data all 2021011101 [5256 B]

Get:6 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 dnsmasq-base amd64 2.86-1.1ubuntu0.3 [354 kB]

Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 docker.io amd64 20.10.21-0ubuntu1~22.04.3 [33.3 MB]

Get:8 http://archive.ubuntu.com/ubuntu jammy/universe amd64 ubuntu-fan all 0.12.16 [35.2 kB]        

Fetched 72.4 MB in 11s (6799 kB/s)                                                                  

Preconfiguring packages ...

Selecting previously unselected package pigz.

(Reading database ... 66255 files and directories currently installed.)

Preparing to unpack .../0-pigz_2.6-1_amd64.deb ...

Unpacking pigz (2.6-1) ...

Selecting previously unselected package bridge-utils.

Preparing to unpack .../1-bridge-utils_1.7-1ubuntu3_amd64.deb ...

Unpacking bridge-utils (1.7-1ubuntu3) ...

Selecting previously unselected package runc.

Preparing to unpack .../2-runc_1.1.4-0ubuntu1~22.04.3_amd64.deb ...

Unpacking runc (1.1.4-0ubuntu1~22.04.3) ...

Selecting previously unselected package containerd.

Preparing to unpack .../3-containerd_1.6.12-0ubuntu1~22.04.3_amd64.deb ...

Unpacking containerd (1.6.12-0ubuntu1~22.04.3) ...

Selecting previously unselected package dns-root-data.

Preparing to unpack .../4-dns-root-data_2021011101_all.deb ...

Unpacking dns-root-data (2021011101) ...

Selecting previously unselected package dnsmasq-base.

Preparing to unpack .../5-dnsmasq-base_2.86-1.1ubuntu0.3_amd64.deb ...

Unpacking dnsmasq-base (2.86-1.1ubuntu0.3) ...

Selecting previously unselected package docker.io.

Preparing to unpack .../6-docker.io_20.10.21-0ubuntu1~22.04.3_amd64.deb ...

Unpacking docker.io (20.10.21-0ubuntu1~22.04.3) ...

Selecting previously unselected package ubuntu-fan.

Preparing to unpack .../7-ubuntu-fan_0.12.16_all.deb ...

Unpacking ubuntu-fan (0.12.16) ...

Setting up dnsmasq-base (2.86-1.1ubuntu0.3) ...

Setting up runc (1.1.4-0ubuntu1~22.04.3) ...

Setting up dns-root-data (2021011101) ...

Setting up bridge-utils (1.7-1ubuntu3) ...

Setting up pigz (2.6-1) ...

Setting up containerd (1.6.12-0ubuntu1~22.04.3) ...

Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.

Setting up ubuntu-fan (0.12.16) ...

Created symlink /etc/systemd/system/multi-user.target.wants/ubuntu-fan.service → /lib/systemd/system/ubuntu-fan.service.

Setting up docker.io (20.10.21-0ubuntu1~22.04.3) ...

Adding group `docker' (GID 123) ...

Done.

Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.

Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.

Processing triggers for dbus (1.12.20-2ubuntu4.1) ...

Processing triggers for man-db (2.10.2-1) ...

Scanning processes...                                                                                

Scanning linux images...                                                                             

  

Running kernel seems to be up-to-date.

  

No services need to be restarted.

  

No containers need to be restarted.

  

No user sessions are running outdated binaries.

  

No VM guests are running outdated hypervisor (qemu) binaries on this host.

root@ubunto:~#
```


# Задача №3

> Запустить контейнер с Ubuntu.


```bash
root@ubunto:~# docker run -d ubuntu

Unable to find image 'ubuntu:latest' locally

latest: Pulling from library/ubuntu

3153aa388d02: Pull complete 

Digest: sha256:0bced47fffa3361afa981854fcabcd4577cd43cebbb808cea2b1f33a3dd7f508

Status: Downloaded newer image for ubuntu:latest

bd1b54d99b2137bb06e4d0764a48266153ead216a129eb37efda4280d1480abb

root@ubunto:~# docker ps -a

CONTAINER ID   IMAGE     COMMAND       CREATED              STATUS                          PORTS     NAMES

bd1b54d99b21   ubuntu    "/bin/bash"   About a minute ago   Exited (0) About a minute ago             nifty_moore

root@ubunto:~#
```


# Задача №4

> Используя Dockerfile, собрать связку nginx + PHP-FPM в одном контейнере.


```bash
root@ubunto:~/mydocker# vim Dockerfile 

root@ubunto:~/mydocker# cat Dockerfile 

FROM ubuntu:latest

MAINTAINER ANA

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install nginx -y && apt install php-fpm -y

VOLUME "/var/www/html"

EXPOSE 80

CMD /usr/sbin/nginx -g "daemon off;"

root@ubunto:~/mydocker# docker build -t test_image .

Sending build context to Docker daemon  2.048kB

Step 1/7 : FROM ubuntu:latest

 ---> 5a81c4b8502e

Step 2/7 : MAINTAINER ANA

 ---> Using cache

 ---> 9dc847287321

Step 3/7 : ARG DEBIAN_FRONTEND=noninteractive

 ---> Running in 0326d0e3fe7e

Removing intermediate container 0326d0e3fe7e

 ---> ebf5b35bb4fd

Step 4/7 : RUN apt-get update && apt-get install nginx -y && apt install php-fpm -y

 ---> Running in 0c037cd35c5d

Get:1 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy InRelease [270 kB]

Get:3 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [44.0 kB]

Get:4 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [952 kB]

Get:5 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [723 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]

Get:7 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [725 kB]

Get:8 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [108 kB]

Get:9 http://archive.ubuntu.com/ubuntu jammy/main amd64 Packages [1792 kB]

Get:10 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [266 kB]

Get:11 http://archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [17.5 MB]

Get:12 http://archive.ubuntu.com/ubuntu jammy/restricted amd64 Packages [164 kB]

Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [1208 kB]

Get:14 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [49.8 kB]

Get:15 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [749 kB]

Get:16 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [1017 kB]

Get:17 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [25.6 kB]

Get:18 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [49.4 kB]

Fetched 25.8 MB in 7s (3571 kB/s)

Reading package lists...

Reading package lists...

Building dependency tree...

Reading state information...

The following additional packages will be installed:

  fontconfig-config fonts-dejavu-core iproute2 libatm1 libbpf0 libbrotli1

  libbsd0 libcap2-bin libdeflate0 libelf1 libexpat1 libfontconfig1

  libfreetype6 libgd3 libicu70 libjbig0 libjpeg-turbo8 libjpeg8 libmaxminddb0

  libmd0 libmnl0 libnginx-mod-http-geoip2 libnginx-mod-http-image-filter

  libnginx-mod-http-xslt-filter libnginx-mod-mail libnginx-mod-stream

  libnginx-mod-stream-geoip2 libpam-cap libpng16-16 libtiff5 libwebp7 libx11-6

  libx11-data libxau6 libxcb1 libxdmcp6 libxml2 libxpm4 libxslt1.1

  libxtables12 nginx-common nginx-core ucf

Suggested packages:

  iproute2-doc libgd-tools mmdb-bin fcgiwrap nginx-doc ssl-cert

The following NEW packages will be installed:

  fontconfig-config fonts-dejavu-core iproute2 libatm1 libbpf0 libbrotli1

  libbsd0 libcap2-bin libdeflate0 libelf1 libexpat1 libfontconfig1

  libfreetype6 libgd3 libicu70 libjbig0 libjpeg-turbo8 libjpeg8 libmaxminddb0

  libmd0 libmnl0 libnginx-mod-http-geoip2 libnginx-mod-http-image-filter

  libnginx-mod-http-xslt-filter libnginx-mod-mail libnginx-mod-stream

  libnginx-mod-stream-geoip2 libpam-cap libpng16-16 libtiff5 libwebp7 libx11-6

  libx11-data libxau6 libxcb1 libxdmcp6 libxml2 libxpm4 libxslt1.1

  libxtables12 nginx nginx-common nginx-core ucf

0 upgraded, 44 newly installed, 0 to remove and 0 not upgraded.

Need to get 17.5 MB of archives.

After this operation, 56.4 MB of additional disk space will be used.

Get:1 http://archive.ubuntu.com/ubuntu jammy/main amd64 libelf1 amd64 0.186-1build1 [51.0 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libbpf0 amd64 1:0.5.0-1ubuntu22.04.1 [140 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmd0 amd64 1.0.4-1build1 [23.0 kB]

Get:4 http://archive.ubuntu.com/ubuntu jammy/main amd64 libbsd0 amd64 0.11.5-1 [44.8 kB]

Get:5 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmnl0 amd64 1.0.4-3build2 [13.2 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libxtables12 amd64 1.8.7-1ubuntu5.1 [31.2 kB]

Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libcap2-bin amd64 1:2.44-1ubuntu0.22.04.1 [26.0 kB]

Get:8 http://archive.ubuntu.com/ubuntu jammy/main amd64 iproute2 amd64 5.15.0-1ubuntu2 [1070 kB]

Get:9 http://archive.ubuntu.com/ubuntu jammy/main amd64 libatm1 amd64 1:2.5.1-4build2 [22.8 kB]

Get:10 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libexpat1 amd64 2.4.7-1ubuntu0.2 [91.0 kB]

Get:11 http://archive.ubuntu.com/ubuntu jammy/main amd64 libicu70 amd64 70.1-2 [10.6 MB]

Get:12 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libpam-cap amd64 1:2.44-1ubuntu0.22.04.1 [7928 B]

Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libxml2 amd64 2.9.13+dfsg-1ubuntu0.3 [763 kB]

Get:14 http://archive.ubuntu.com/ubuntu jammy/main amd64 ucf all 3.0043 [56.1 kB]

Get:15 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmaxminddb0 amd64 1.5.2-1build2 [24.7 kB]

Get:16 http://archive.ubuntu.com/ubuntu jammy/main amd64 libpng16-16 amd64 1.6.37-3build5 [191 kB]

Get:17 http://archive.ubuntu.com/ubuntu jammy/main amd64 libxau6 amd64 1:1.0.9-1build5 [7634 B]

Get:18 http://archive.ubuntu.com/ubuntu jammy/main amd64 libxdmcp6 amd64 1:1.1.3-0ubuntu5 [10.9 kB]

Get:19 http://archive.ubuntu.com/ubuntu jammy/main amd64 libxcb1 amd64 1.14-3ubuntu3 [49.0 kB]

Get:20 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libx11-data all 2:1.7.5-1ubuntu0.2 [119 kB]

Get:21 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libx11-6 amd64 2:1.7.5-1ubuntu0.2 [666 kB]

Get:22 http://archive.ubuntu.com/ubuntu jammy/main amd64 fonts-dejavu-core all 2.37-2build1 [1041 kB]

Get:23 http://archive.ubuntu.com/ubuntu jammy/main amd64 fontconfig-config all 2.13.1-4.2ubuntu5 [29.1 kB]

Get:24 http://archive.ubuntu.com/ubuntu jammy/main amd64 libbrotli1 amd64 1.0.9-2build6 [315 kB]

Get:25 http://archive.ubuntu.com/ubuntu jammy/main amd64 libdeflate0 amd64 1.10-2 [70.9 kB]

Get:26 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libfreetype6 amd64 2.11.1+dfsg-1ubuntu0.2 [389 kB]

Get:27 http://archive.ubuntu.com/ubuntu jammy/main amd64 libfontconfig1 amd64 2.13.1-4.2ubuntu5 [131 kB]

Get:28 http://archive.ubuntu.com/ubuntu jammy/main amd64 libjpeg-turbo8 amd64 2.1.2-0ubuntu1 [134 kB]

Get:29 http://archive.ubuntu.com/ubuntu jammy/main amd64 libjpeg8 amd64 8c-2ubuntu10 [2264 B]

Get:30 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libjbig0 amd64 2.1-3.1ubuntu0.22.04.1 [29.2 kB]

Get:31 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libwebp7 amd64 1.2.2-2ubuntu0.22.04.1 [206 kB]

Get:32 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libtiff5 amd64 4.3.0-6ubuntu0.4 [183 kB]

Get:33 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libxpm4 amd64 1:3.5.12-1ubuntu0.22.04.1 [36.4 kB]

Get:34 http://archive.ubuntu.com/ubuntu jammy/main amd64 libgd3 amd64 2.3.0-2ubuntu2 [129 kB]

Get:35 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx-common all 1.18.0-6ubuntu14.4 [40.0 kB]

Get:36 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-geoip2 amd64 1.18.0-6ubuntu14.4 [11.9 kB]

Get:37 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-image-filter amd64 1.18.0-6ubuntu14.4 [15.4 kB]

Get:38 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libxslt1.1 amd64 1.1.34-4ubuntu0.22.04.1 [164 kB]

Get:39 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-xslt-filter amd64 1.18.0-6ubuntu14.4 [13.7 kB]

Get:40 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-mail amd64 1.18.0-6ubuntu14.4 [45.7 kB]

Get:41 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-stream amd64 1.18.0-6ubuntu14.4 [72.9 kB]

Get:42 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-stream-geoip2 amd64 1.18.0-6ubuntu14.4 [10.1 kB]

Get:43 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx-core amd64 1.18.0-6ubuntu14.4 [484 kB]

Get:44 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx amd64 1.18.0-6ubuntu14.4 [3872 B]

debconf: delaying package configuration, since apt-utils is not installed

Fetched 17.5 MB in 9s (2013 kB/s)

Selecting previously unselected package libelf1:amd64.

(Reading database ... 4395 files and directories currently installed.)

Preparing to unpack .../00-libelf1_0.186-1build1_amd64.deb ...

Unpacking libelf1:amd64 (0.186-1build1) ...

Selecting previously unselected package libbpf0:amd64.

Preparing to unpack .../01-libbpf0_1%3a0.5.0-1ubuntu22.04.1_amd64.deb ...

Unpacking libbpf0:amd64 (1:0.5.0-1ubuntu22.04.1) ...

Selecting previously unselected package libmd0:amd64.

Preparing to unpack .../02-libmd0_1.0.4-1build1_amd64.deb ...

Unpacking libmd0:amd64 (1.0.4-1build1) ...

Selecting previously unselected package libbsd0:amd64.

Preparing to unpack .../03-libbsd0_0.11.5-1_amd64.deb ...

Unpacking libbsd0:amd64 (0.11.5-1) ...

Selecting previously unselected package libmnl0:amd64.

Preparing to unpack .../04-libmnl0_1.0.4-3build2_amd64.deb ...

Unpacking libmnl0:amd64 (1.0.4-3build2) ...

Selecting previously unselected package libxtables12:amd64.

Preparing to unpack .../05-libxtables12_1.8.7-1ubuntu5.1_amd64.deb ...

Unpacking libxtables12:amd64 (1.8.7-1ubuntu5.1) ...

Selecting previously unselected package libcap2-bin.

Preparing to unpack .../06-libcap2-bin_1%3a2.44-1ubuntu0.22.04.1_amd64.deb ...

Unpacking libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...

Selecting previously unselected package iproute2.

Preparing to unpack .../07-iproute2_5.15.0-1ubuntu2_amd64.deb ...

Unpacking iproute2 (5.15.0-1ubuntu2) ...

Selecting previously unselected package libatm1:amd64.

Preparing to unpack .../08-libatm1_1%3a2.5.1-4build2_amd64.deb ...

Unpacking libatm1:amd64 (1:2.5.1-4build2) ...

Selecting previously unselected package libexpat1:amd64.

Preparing to unpack .../09-libexpat1_2.4.7-1ubuntu0.2_amd64.deb ...

Unpacking libexpat1:amd64 (2.4.7-1ubuntu0.2) ...

Selecting previously unselected package libicu70:amd64.

Preparing to unpack .../10-libicu70_70.1-2_amd64.deb ...

Unpacking libicu70:amd64 (70.1-2) ...

Selecting previously unselected package libpam-cap:amd64.

Preparing to unpack .../11-libpam-cap_1%3a2.44-1ubuntu0.22.04.1_amd64.deb ...

Unpacking libpam-cap:amd64 (1:2.44-1ubuntu0.22.04.1) ...

Selecting previously unselected package libxml2:amd64.

Preparing to unpack .../12-libxml2_2.9.13+dfsg-1ubuntu0.3_amd64.deb ...

Unpacking libxml2:amd64 (2.9.13+dfsg-1ubuntu0.3) ...

Selecting previously unselected package ucf.

Preparing to unpack .../13-ucf_3.0043_all.deb ...

Moving old data out of the way

Unpacking ucf (3.0043) ...

Selecting previously unselected package libmaxminddb0:amd64.

Preparing to unpack .../14-libmaxminddb0_1.5.2-1build2_amd64.deb ...

Unpacking libmaxminddb0:amd64 (1.5.2-1build2) ...

Selecting previously unselected package libpng16-16:amd64.

Preparing to unpack .../15-libpng16-16_1.6.37-3build5_amd64.deb ...

Unpacking libpng16-16:amd64 (1.6.37-3build5) ...

Selecting previously unselected package libxau6:amd64.

Preparing to unpack .../16-libxau6_1%3a1.0.9-1build5_amd64.deb ...

Unpacking libxau6:amd64 (1:1.0.9-1build5) ...

Selecting previously unselected package libxdmcp6:amd64.

Preparing to unpack .../17-libxdmcp6_1%3a1.1.3-0ubuntu5_amd64.deb ...

Unpacking libxdmcp6:amd64 (1:1.1.3-0ubuntu5) ...

Selecting previously unselected package libxcb1:amd64.

Preparing to unpack .../18-libxcb1_1.14-3ubuntu3_amd64.deb ...

Unpacking libxcb1:amd64 (1.14-3ubuntu3) ...

Selecting previously unselected package libx11-data.

Preparing to unpack .../19-libx11-data_2%3a1.7.5-1ubuntu0.2_all.deb ...

Unpacking libx11-data (2:1.7.5-1ubuntu0.2) ...

Selecting previously unselected package libx11-6:amd64.

Preparing to unpack .../20-libx11-6_2%3a1.7.5-1ubuntu0.2_amd64.deb ...

Unpacking libx11-6:amd64 (2:1.7.5-1ubuntu0.2) ...

Selecting previously unselected package fonts-dejavu-core.

Preparing to unpack .../21-fonts-dejavu-core_2.37-2build1_all.deb ...

Unpacking fonts-dejavu-core (2.37-2build1) ...

Selecting previously unselected package fontconfig-config.

Preparing to unpack .../22-fontconfig-config_2.13.1-4.2ubuntu5_all.deb ...

Unpacking fontconfig-config (2.13.1-4.2ubuntu5) ...

Selecting previously unselected package libbrotli1:amd64.

Preparing to unpack .../23-libbrotli1_1.0.9-2build6_amd64.deb ...

Unpacking libbrotli1:amd64 (1.0.9-2build6) ...

Selecting previously unselected package libdeflate0:amd64.

Preparing to unpack .../24-libdeflate0_1.10-2_amd64.deb ...

Unpacking libdeflate0:amd64 (1.10-2) ...

Selecting previously unselected package libfreetype6:amd64.

Preparing to unpack .../25-libfreetype6_2.11.1+dfsg-1ubuntu0.2_amd64.deb ...

Unpacking libfreetype6:amd64 (2.11.1+dfsg-1ubuntu0.2) ...

Selecting previously unselected package libfontconfig1:amd64.

Preparing to unpack .../26-libfontconfig1_2.13.1-4.2ubuntu5_amd64.deb ...

Unpacking libfontconfig1:amd64 (2.13.1-4.2ubuntu5) ...

Selecting previously unselected package libjpeg-turbo8:amd64.

Preparing to unpack .../27-libjpeg-turbo8_2.1.2-0ubuntu1_amd64.deb ...

Unpacking libjpeg-turbo8:amd64 (2.1.2-0ubuntu1) ...

Selecting previously unselected package libjpeg8:amd64.

Preparing to unpack .../28-libjpeg8_8c-2ubuntu10_amd64.deb ...

Unpacking libjpeg8:amd64 (8c-2ubuntu10) ...

Selecting previously unselected package libjbig0:amd64.

Preparing to unpack .../29-libjbig0_2.1-3.1ubuntu0.22.04.1_amd64.deb ...

Unpacking libjbig0:amd64 (2.1-3.1ubuntu0.22.04.1) ...

Selecting previously unselected package libwebp7:amd64.

Preparing to unpack .../30-libwebp7_1.2.2-2ubuntu0.22.04.1_amd64.deb ...

Unpacking libwebp7:amd64 (1.2.2-2ubuntu0.22.04.1) ...

Selecting previously unselected package libtiff5:amd64.

Preparing to unpack .../31-libtiff5_4.3.0-6ubuntu0.4_amd64.deb ...

Unpacking libtiff5:amd64 (4.3.0-6ubuntu0.4) ...

Selecting previously unselected package libxpm4:amd64.

Preparing to unpack .../32-libxpm4_1%3a3.5.12-1ubuntu0.22.04.1_amd64.deb ...

Unpacking libxpm4:amd64 (1:3.5.12-1ubuntu0.22.04.1) ...

Selecting previously unselected package libgd3:amd64.

Preparing to unpack .../33-libgd3_2.3.0-2ubuntu2_amd64.deb ...

Unpacking libgd3:amd64 (2.3.0-2ubuntu2) ...

Selecting previously unselected package nginx-common.

Preparing to unpack .../34-nginx-common_1.18.0-6ubuntu14.4_all.deb ...

Unpacking nginx-common (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-geoip2.

Preparing to unpack .../35-libnginx-mod-http-geoip2_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-geoip2 (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-image-filter.

Preparing to unpack .../36-libnginx-mod-http-image-filter_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-image-filter (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libxslt1.1:amd64.

Preparing to unpack .../37-libxslt1.1_1.1.34-4ubuntu0.22.04.1_amd64.deb ...

Unpacking libxslt1.1:amd64 (1.1.34-4ubuntu0.22.04.1) ...

Selecting previously unselected package libnginx-mod-http-xslt-filter.

Preparing to unpack .../38-libnginx-mod-http-xslt-filter_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-xslt-filter (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-mail.

Preparing to unpack .../39-libnginx-mod-mail_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-mail (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-stream.

Preparing to unpack .../40-libnginx-mod-stream_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-stream (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-stream-geoip2.

Preparing to unpack .../41-libnginx-mod-stream-geoip2_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-stream-geoip2 (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package nginx-core.

Preparing to unpack .../42-nginx-core_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking nginx-core (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package nginx.

Preparing to unpack .../43-nginx_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking nginx (1.18.0-6ubuntu14.4) ...

Setting up libexpat1:amd64 (2.4.7-1ubuntu0.2) ...

Setting up libxau6:amd64 (1:1.0.9-1build5) ...

Setting up libmaxminddb0:amd64 (1.5.2-1build2) ...

Setting up libbrotli1:amd64 (1.0.9-2build6) ...

Setting up libdeflate0:amd64 (1.10-2) ...

Setting up nginx-common (1.18.0-6ubuntu14.4) ...

Setting up libatm1:amd64 (1:2.5.1-4build2) ...

Setting up libjbig0:amd64 (2.1-3.1ubuntu0.22.04.1) ...

Setting up libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...

Setting up libx11-data (2:1.7.5-1ubuntu0.2) ...

Setting up libpng16-16:amd64 (1.6.37-3build5) ...

Setting up libmnl0:amd64 (1.0.4-3build2) ...

Setting up fonts-dejavu-core (2.37-2build1) ...

Setting up ucf (3.0043) ...

Setting up libjpeg-turbo8:amd64 (2.1.2-0ubuntu1) ...

Setting up libxtables12:amd64 (1.8.7-1ubuntu5.1) ...

Setting up libwebp7:amd64 (1.2.2-2ubuntu0.22.04.1) ...

Setting up libmd0:amd64 (1.0.4-1build1) ...

Setting up libnginx-mod-http-geoip2 (1.18.0-6ubuntu14.4) ...

Setting up libbsd0:amd64 (0.11.5-1) ...

Setting up libelf1:amd64 (0.186-1build1) ...

Setting up libpam-cap:amd64 (1:2.44-1ubuntu0.22.04.1) ...

Setting up libicu70:amd64 (70.1-2) ...

Setting up libjpeg8:amd64 (8c-2ubuntu10) ...

Setting up libnginx-mod-mail (1.18.0-6ubuntu14.4) ...

Setting up libxdmcp6:amd64 (1:1.1.3-0ubuntu5) ...

Setting up libxcb1:amd64 (1.14-3ubuntu3) ...

Setting up fontconfig-config (2.13.1-4.2ubuntu5) ...

Setting up libnginx-mod-stream (1.18.0-6ubuntu14.4) ...

Setting up libfreetype6:amd64 (2.11.1+dfsg-1ubuntu0.2) ...

Setting up libx11-6:amd64 (2:1.7.5-1ubuntu0.2) ...

Setting up libtiff5:amd64 (4.3.0-6ubuntu0.4) ...

Setting up libfontconfig1:amd64 (2.13.1-4.2ubuntu5) ...

Setting up libbpf0:amd64 (1:0.5.0-1ubuntu22.04.1) ...

Setting up libnginx-mod-stream-geoip2 (1.18.0-6ubuntu14.4) ...

Setting up libxml2:amd64 (2.9.13+dfsg-1ubuntu0.3) ...

Setting up libxpm4:amd64 (1:3.5.12-1ubuntu0.22.04.1) ...

Setting up iproute2 (5.15.0-1ubuntu2) ...

Setting up libgd3:amd64 (2.3.0-2ubuntu2) ...

Setting up libxslt1.1:amd64 (1.1.34-4ubuntu0.22.04.1) ...

Setting up libnginx-mod-http-image-filter (1.18.0-6ubuntu14.4) ...

Setting up libnginx-mod-http-xslt-filter (1.18.0-6ubuntu14.4) ...

Setting up nginx-core (1.18.0-6ubuntu14.4) ...

invoke-rc.d: could not determine current runlevel

invoke-rc.d: policy-rc.d denied execution of start.

Setting up nginx (1.18.0-6ubuntu14.4) ...

Processing triggers for libc-bin (2.35-0ubuntu3.1) ...

  

WARNING: apt does not have a stable CLI interface. Use with caution in scripts.

  

Reading package lists...

Building dependency tree...

Reading state information...

The following additional packages will be installed:

  bzip2 dbus dmsetup file gir1.2-glib-2.0 libapparmor1 libargon2-1

  libcryptsetup12 libdbus-1-3 libdevmapper1.02.1 libedit2 libgdbm-compat4

  libgdbm6 libgirepository-1.0-1 libglib2.0-0 libglib2.0-data libip4tc2

  libjson-c5 libkmod2 libmagic-mgc libmagic1 libmpdec3 libperl5.34

  libpython3-stdlib libpython3.10-minimal libpython3.10-stdlib libreadline8

  libsodium23 libsqlite3-0 mailcap media-types mime-support netbase

  networkd-dispatcher perl perl-modules-5.34 php-common php8.1-cli

  php8.1-common php8.1-fpm php8.1-opcache php8.1-readline psmisc python3

  python3-dbus python3-gi python3-minimal python3.10 python3.10-minimal

  readline-common shared-mime-info systemd systemd-timesyncd tzdata

  xdg-user-dirs xz-utils

Suggested packages:

  bzip2-doc default-dbus-session-bus | dbus-session-bus gdbm-l10n iw

  | wireless-tools perl-doc libterm-readline-gnu-perl

  | libterm-readline-perl-perl make libtap-harness-archive-perl php-pear

  python3-doc python3-tk python3-venv python-dbus-doc python3.10-venv

  python3.10-doc binutils binfmt-support readline-doc systemd-container

  libfido2-1 libtss2-esys-3.0.2-0 libtss2-mu0 libtss2-rc0 policykit-1

The following NEW packages will be installed:

  bzip2 dbus dmsetup file gir1.2-glib-2.0 libapparmor1 libargon2-1

  libcryptsetup12 libdbus-1-3 libdevmapper1.02.1 libedit2 libgdbm-compat4

  libgdbm6 libgirepository-1.0-1 libglib2.0-0 libglib2.0-data libip4tc2

  libjson-c5 libkmod2 libmagic-mgc libmagic1 libmpdec3 libperl5.34

  libpython3-stdlib libpython3.10-minimal libpython3.10-stdlib libreadline8

  libsodium23 libsqlite3-0 mailcap media-types mime-support netbase

  networkd-dispatcher perl perl-modules-5.34 php-common php-fpm php8.1-cli

  php8.1-common php8.1-fpm php8.1-opcache php8.1-readline psmisc python3

  python3-dbus python3-gi python3-minimal python3.10 python3.10-minimal

  readline-common shared-mime-info systemd systemd-timesyncd tzdata

  xdg-user-dirs xz-utils

0 upgraded, 57 newly installed, 0 to remove and 0 not upgraded.

Need to get 29.0 MB of archives.

After this operation, 136 MB of additional disk space will be used.

Get:1 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libpython3.10-minimal amd64 3.10.6-1~22.04.2ubuntu1.1 [810 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 python3.10-minimal amd64 3.10.6-1~22.04.2ubuntu1.1 [2262 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 python3-minimal amd64 3.10.6-1~22.04 [24.3 kB]

Get:4 http://archive.ubuntu.com/ubuntu jammy/main amd64 media-types all 7.0.0 [25.5 kB]

Get:5 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 perl-modules-5.34 all 5.34.0-3ubuntu1.2 [2977 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy/main amd64 libgdbm6 amd64 1.23-1 [33.9 kB]

Get:7 http://archive.ubuntu.com/ubuntu jammy/main amd64 libgdbm-compat4 amd64 1.23-1 [6606 B]

Get:8 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libperl5.34 amd64 5.34.0-3ubuntu1.2 [4818 kB]

Get:9 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 perl amd64 5.34.0-3ubuntu1.2 [232 kB]

Get:10 http://archive.ubuntu.com/ubuntu jammy/main amd64 mailcap all 3.70+nmu1ubuntu1 [23.8 kB]

Get:11 http://archive.ubuntu.com/ubuntu jammy/main amd64 mime-support all 3.66 [3696 B]

Get:12 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmpdec3 amd64 2.5.1-2build2 [86.8 kB]

Get:13 http://archive.ubuntu.com/ubuntu jammy/main amd64 readline-common all 8.1.2-1 [53.5 kB]

Get:14 http://archive.ubuntu.com/ubuntu jammy/main amd64 libreadline8 amd64 8.1.2-1 [153 kB]

Get:15 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libsqlite3-0 amd64 3.37.2-2ubuntu0.1 [641 kB]

Get:16 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libpython3.10-stdlib amd64 3.10.6-1~22.04.2ubuntu1.1 [1832 kB]

Get:17 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 python3.10 amd64 3.10.6-1~22.04.2ubuntu1.1 [497 kB]

Get:18 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libpython3-stdlib amd64 3.10.6-1~22.04 [6910 B]

Get:19 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 python3 amd64 3.10.6-1~22.04 [22.8 kB]

Get:20 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libapparmor1 amd64 3.0.4-2ubuntu2.2 [39.2 kB]

Get:21 http://archive.ubuntu.com/ubuntu jammy/main amd64 libargon2-1 amd64 0~20171227-0.3 [19.5 kB]

Get:22 http://archive.ubuntu.com/ubuntu jammy/main amd64 libdevmapper1.02.1 amd64 2:1.02.175-2.1ubuntu4 [139 kB]

Get:23 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libjson-c5 amd64 0.15-3~ubuntu1.22.04.1 [33.5 kB]

Get:24 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libcryptsetup12 amd64 2:2.4.3-1ubuntu1.1 [211 kB]

Get:25 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libip4tc2 amd64 1.8.7-1ubuntu5.1 [19.8 kB]

Get:26 http://archive.ubuntu.com/ubuntu jammy/main amd64 libkmod2 amd64 29-1ubuntu1 [48.0 kB]

Get:27 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 systemd amd64 249.11-0ubuntu3.9 [4581 kB]

Get:28 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libdbus-1-3 amd64 1.12.20-2ubuntu4.1 [189 kB]

Get:29 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 dbus amd64 1.12.20-2ubuntu4.1 [158 kB]

Get:30 http://archive.ubuntu.com/ubuntu jammy/main amd64 dmsetup amd64 2:1.02.175-2.1ubuntu4 [81.7 kB]

Get:31 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libglib2.0-0 amd64 2.72.4-0ubuntu2.2 [1463 kB]

Get:32 http://archive.ubuntu.com/ubuntu jammy/main amd64 libgirepository-1.0-1 amd64 1.72.0-1 [55.6 kB]

Get:33 http://archive.ubuntu.com/ubuntu jammy/main amd64 gir1.2-glib-2.0 amd64 1.72.0-1 [164 kB]

Get:34 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libglib2.0-data all 2.72.4-0ubuntu2.2 [4612 B]

Get:35 http://archive.ubuntu.com/ubuntu jammy/main amd64 netbase all 6.3 [12.9 kB]

Get:36 http://archive.ubuntu.com/ubuntu jammy/main amd64 python3-dbus amd64 1.2.18-3build1 [99.5 kB]

Get:37 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 python3-gi amd64 3.42.1-0ubuntu1 [229 kB]

Get:38 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 networkd-dispatcher all 2.1-2ubuntu0.22.04.2 [15.8 kB]

Get:39 http://archive.ubuntu.com/ubuntu jammy/main amd64 shared-mime-info amd64 2.1-2 [454 kB]

Get:40 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 systemd-timesyncd amd64 249.11-0ubuntu3.9 [31.2 kB]

Get:41 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 tzdata all 2023c-0ubuntu0.22.04.2 [349 kB]

Get:42 http://archive.ubuntu.com/ubuntu jammy/main amd64 xdg-user-dirs amd64 0.17-2ubuntu4 [53.9 kB]

Get:43 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmagic-mgc amd64 1:5.41-3 [257 kB]

Get:44 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmagic1 amd64 1:5.41-3 [87.2 kB]

Get:45 http://archive.ubuntu.com/ubuntu jammy/main amd64 file amd64 1:5.41-3 [21.5 kB]

Get:46 http://archive.ubuntu.com/ubuntu jammy/main amd64 libedit2 amd64 3.1-20210910-1build1 [96.8 kB]

Get:47 http://archive.ubuntu.com/ubuntu jammy/main amd64 psmisc amd64 23.4-2build3 [119 kB]

Get:48 http://archive.ubuntu.com/ubuntu jammy/main amd64 xz-utils amd64 5.2.5-2ubuntu1 [84.8 kB]

Get:49 http://archive.ubuntu.com/ubuntu jammy/main amd64 bzip2 amd64 1.0.8-5build1 [34.8 kB]

Get:50 http://archive.ubuntu.com/ubuntu jammy/main amd64 libsodium23 amd64 1.0.18-1build2 [164 kB]

Get:51 http://archive.ubuntu.com/ubuntu jammy/main amd64 php-common all 2:92ubuntu1 [12.4 kB]

Get:52 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-common amd64 8.1.2-1ubuntu2.13 [1125 kB]

Get:53 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-opcache amd64 8.1.2-1ubuntu2.13 [365 kB]

Get:54 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-readline amd64 8.1.2-1ubuntu2.13 [13.5 kB]

Get:55 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-cli amd64 8.1.2-1ubuntu2.13 [1833 kB]

Get:56 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 php8.1-fpm amd64 8.1.2-1ubuntu2.13 [1840 kB]

Get:57 http://archive.ubuntu.com/ubuntu jammy/universe amd64 php-fpm all 2:8.1+92ubuntu1 [2838 B]

debconf: delaying package configuration, since apt-utils is not installed

Fetched 29.0 MB in 13s (2188 kB/s)

Selecting previously unselected package libpython3.10-minimal:amd64.

(Reading database ... 5298 files and directories currently installed.)

Preparing to unpack .../libpython3.10-minimal_3.10.6-1~22.04.2ubuntu1.1_amd64.deb ...

Unpacking libpython3.10-minimal:amd64 (3.10.6-1~22.04.2ubuntu1.1) ...

Selecting previously unselected package python3.10-minimal.

Preparing to unpack .../python3.10-minimal_3.10.6-1~22.04.2ubuntu1.1_amd64.deb ...

Unpacking python3.10-minimal (3.10.6-1~22.04.2ubuntu1.1) ...

Setting up libpython3.10-minimal:amd64 (3.10.6-1~22.04.2ubuntu1.1) ...

Setting up python3.10-minimal (3.10.6-1~22.04.2ubuntu1.1) ...

Selecting previously unselected package python3-minimal.

(Reading database ... 5592 files and directories currently installed.)

Preparing to unpack .../00-python3-minimal_3.10.6-1~22.04_amd64.deb ...

Unpacking python3-minimal (3.10.6-1~22.04) ...

Selecting previously unselected package media-types.

Preparing to unpack .../01-media-types_7.0.0_all.deb ...

Unpacking media-types (7.0.0) ...

Selecting previously unselected package perl-modules-5.34.

Preparing to unpack .../02-perl-modules-5.34_5.34.0-3ubuntu1.2_all.deb ...

Unpacking perl-modules-5.34 (5.34.0-3ubuntu1.2) ...

Selecting previously unselected package libgdbm6:amd64.

Preparing to unpack .../03-libgdbm6_1.23-1_amd64.deb ...

Unpacking libgdbm6:amd64 (1.23-1) ...

Selecting previously unselected package libgdbm-compat4:amd64.

Preparing to unpack .../04-libgdbm-compat4_1.23-1_amd64.deb ...

Unpacking libgdbm-compat4:amd64 (1.23-1) ...

Selecting previously unselected package libperl5.34:amd64.

Preparing to unpack .../05-libperl5.34_5.34.0-3ubuntu1.2_amd64.deb ...

Unpacking libperl5.34:amd64 (5.34.0-3ubuntu1.2) ...

Selecting previously unselected package perl.

Preparing to unpack .../06-perl_5.34.0-3ubuntu1.2_amd64.deb ...

Unpacking perl (5.34.0-3ubuntu1.2) ...

Selecting previously unselected package mailcap.

Preparing to unpack .../07-mailcap_3.70+nmu1ubuntu1_all.deb ...

Unpacking mailcap (3.70+nmu1ubuntu1) ...

Selecting previously unselected package mime-support.

Preparing to unpack .../08-mime-support_3.66_all.deb ...

Unpacking mime-support (3.66) ...

Selecting previously unselected package libmpdec3:amd64.

Preparing to unpack .../09-libmpdec3_2.5.1-2build2_amd64.deb ...

Unpacking libmpdec3:amd64 (2.5.1-2build2) ...

Selecting previously unselected package readline-common.

Preparing to unpack .../10-readline-common_8.1.2-1_all.deb ...

Unpacking readline-common (8.1.2-1) ...

Selecting previously unselected package libreadline8:amd64.

Preparing to unpack .../11-libreadline8_8.1.2-1_amd64.deb ...

Unpacking libreadline8:amd64 (8.1.2-1) ...

Selecting previously unselected package libsqlite3-0:amd64.

Preparing to unpack .../12-libsqlite3-0_3.37.2-2ubuntu0.1_amd64.deb ...

Unpacking libsqlite3-0:amd64 (3.37.2-2ubuntu0.1) ...

Selecting previously unselected package libpython3.10-stdlib:amd64.

Preparing to unpack .../13-libpython3.10-stdlib_3.10.6-1~22.04.2ubuntu1.1_amd64.deb ...

Unpacking libpython3.10-stdlib:amd64 (3.10.6-1~22.04.2ubuntu1.1) ...

Selecting previously unselected package python3.10.

Preparing to unpack .../14-python3.10_3.10.6-1~22.04.2ubuntu1.1_amd64.deb ...

Unpacking python3.10 (3.10.6-1~22.04.2ubuntu1.1) ...

Selecting previously unselected package libpython3-stdlib:amd64.

Preparing to unpack .../15-libpython3-stdlib_3.10.6-1~22.04_amd64.deb ...

Unpacking libpython3-stdlib:amd64 (3.10.6-1~22.04) ...

Setting up python3-minimal (3.10.6-1~22.04) ...

Selecting previously unselected package python3.

(Reading database ... 8034 files and directories currently installed.)

Preparing to unpack .../00-python3_3.10.6-1~22.04_amd64.deb ...

Unpacking python3 (3.10.6-1~22.04) ...

Selecting previously unselected package libapparmor1:amd64.

Preparing to unpack .../01-libapparmor1_3.0.4-2ubuntu2.2_amd64.deb ...

Unpacking libapparmor1:amd64 (3.0.4-2ubuntu2.2) ...

Selecting previously unselected package libargon2-1:amd64.

Preparing to unpack .../02-libargon2-1_0~20171227-0.3_amd64.deb ...

Unpacking libargon2-1:amd64 (0~20171227-0.3) ...

Selecting previously unselected package libdevmapper1.02.1:amd64.

Preparing to unpack .../03-libdevmapper1.02.1_2%3a1.02.175-2.1ubuntu4_amd64.deb ...

Unpacking libdevmapper1.02.1:amd64 (2:1.02.175-2.1ubuntu4) ...

Selecting previously unselected package libjson-c5:amd64.

Preparing to unpack .../04-libjson-c5_0.15-3~ubuntu1.22.04.1_amd64.deb ...

Unpacking libjson-c5:amd64 (0.15-3~ubuntu1.22.04.1) ...

Selecting previously unselected package libcryptsetup12:amd64.

Preparing to unpack .../05-libcryptsetup12_2%3a2.4.3-1ubuntu1.1_amd64.deb ...

Unpacking libcryptsetup12:amd64 (2:2.4.3-1ubuntu1.1) ...

Selecting previously unselected package libip4tc2:amd64.

Preparing to unpack .../06-libip4tc2_1.8.7-1ubuntu5.1_amd64.deb ...

Unpacking libip4tc2:amd64 (1.8.7-1ubuntu5.1) ...

Selecting previously unselected package libkmod2:amd64.

Preparing to unpack .../07-libkmod2_29-1ubuntu1_amd64.deb ...

Unpacking libkmod2:amd64 (29-1ubuntu1) ...

Selecting previously unselected package systemd.

Preparing to unpack .../08-systemd_249.11-0ubuntu3.9_amd64.deb ...

Unpacking systemd (249.11-0ubuntu3.9) ...

Selecting previously unselected package libdbus-1-3:amd64.

Preparing to unpack .../09-libdbus-1-3_1.12.20-2ubuntu4.1_amd64.deb ...

Unpacking libdbus-1-3:amd64 (1.12.20-2ubuntu4.1) ...

Selecting previously unselected package dbus.

Preparing to unpack .../10-dbus_1.12.20-2ubuntu4.1_amd64.deb ...

Unpacking dbus (1.12.20-2ubuntu4.1) ...

Selecting previously unselected package dmsetup.

Preparing to unpack .../11-dmsetup_2%3a1.02.175-2.1ubuntu4_amd64.deb ...

Unpacking dmsetup (2:1.02.175-2.1ubuntu4) ...

Selecting previously unselected package libglib2.0-0:amd64.

Preparing to unpack .../12-libglib2.0-0_2.72.4-0ubuntu2.2_amd64.deb ...

Unpacking libglib2.0-0:amd64 (2.72.4-0ubuntu2.2) ...

Selecting previously unselected package libgirepository-1.0-1:amd64.

Preparing to unpack .../13-libgirepository-1.0-1_1.72.0-1_amd64.deb ...

Unpacking libgirepository-1.0-1:amd64 (1.72.0-1) ...

Selecting previously unselected package gir1.2-glib-2.0:amd64.

Preparing to unpack .../14-gir1.2-glib-2.0_1.72.0-1_amd64.deb ...

Unpacking gir1.2-glib-2.0:amd64 (1.72.0-1) ...

Selecting previously unselected package libglib2.0-data.

Preparing to unpack .../15-libglib2.0-data_2.72.4-0ubuntu2.2_all.deb ...

Unpacking libglib2.0-data (2.72.4-0ubuntu2.2) ...

Selecting previously unselected package netbase.

Preparing to unpack .../16-netbase_6.3_all.deb ...

Unpacking netbase (6.3) ...

Selecting previously unselected package python3-dbus.

Preparing to unpack .../17-python3-dbus_1.2.18-3build1_amd64.deb ...

Unpacking python3-dbus (1.2.18-3build1) ...

Selecting previously unselected package python3-gi.

Preparing to unpack .../18-python3-gi_3.42.1-0ubuntu1_amd64.deb ...

Unpacking python3-gi (3.42.1-0ubuntu1) ...

Selecting previously unselected package networkd-dispatcher.

Preparing to unpack .../19-networkd-dispatcher_2.1-2ubuntu0.22.04.2_all.deb ...

Unpacking networkd-dispatcher (2.1-2ubuntu0.22.04.2) ...

Selecting previously unselected package shared-mime-info.

Preparing to unpack .../20-shared-mime-info_2.1-2_amd64.deb ...

Unpacking shared-mime-info (2.1-2) ...

Selecting previously unselected package systemd-timesyncd.

Preparing to unpack .../21-systemd-timesyncd_249.11-0ubuntu3.9_amd64.deb ...

Unpacking systemd-timesyncd (249.11-0ubuntu3.9) ...

Selecting previously unselected package tzdata.

Preparing to unpack .../22-tzdata_2023c-0ubuntu0.22.04.2_all.deb ...

Unpacking tzdata (2023c-0ubuntu0.22.04.2) ...

Selecting previously unselected package xdg-user-dirs.

Preparing to unpack .../23-xdg-user-dirs_0.17-2ubuntu4_amd64.deb ...

Unpacking xdg-user-dirs (0.17-2ubuntu4) ...

Selecting previously unselected package libmagic-mgc.

Preparing to unpack .../24-libmagic-mgc_1%3a5.41-3_amd64.deb ...

Unpacking libmagic-mgc (1:5.41-3) ...

Selecting previously unselected package libmagic1:amd64.

Preparing to unpack .../25-libmagic1_1%3a5.41-3_amd64.deb ...

Unpacking libmagic1:amd64 (1:5.41-3) ...

Selecting previously unselected package file.

Preparing to unpack .../26-file_1%3a5.41-3_amd64.deb ...

Unpacking file (1:5.41-3) ...

Selecting previously unselected package libedit2:amd64.

Preparing to unpack .../27-libedit2_3.1-20210910-1build1_amd64.deb ...

Unpacking libedit2:amd64 (3.1-20210910-1build1) ...

Selecting previously unselected package psmisc.

Preparing to unpack .../28-psmisc_23.4-2build3_amd64.deb ...

Unpacking psmisc (23.4-2build3) ...

Selecting previously unselected package xz-utils.

Preparing to unpack .../29-xz-utils_5.2.5-2ubuntu1_amd64.deb ...

Unpacking xz-utils (5.2.5-2ubuntu1) ...

Selecting previously unselected package bzip2.

Preparing to unpack .../30-bzip2_1.0.8-5build1_amd64.deb ...

Unpacking bzip2 (1.0.8-5build1) ...

Selecting previously unselected package libsodium23:amd64.

Preparing to unpack .../31-libsodium23_1.0.18-1build2_amd64.deb ...

Unpacking libsodium23:amd64 (1.0.18-1build2) ...

Selecting previously unselected package php-common.

Preparing to unpack .../32-php-common_2%3a92ubuntu1_all.deb ...

Unpacking php-common (2:92ubuntu1) ...

Selecting previously unselected package php8.1-common.

Preparing to unpack .../33-php8.1-common_8.1.2-1ubuntu2.13_amd64.deb ...

Unpacking php8.1-common (8.1.2-1ubuntu2.13) ...

Selecting previously unselected package php8.1-opcache.

Preparing to unpack .../34-php8.1-opcache_8.1.2-1ubuntu2.13_amd64.deb ...

Unpacking php8.1-opcache (8.1.2-1ubuntu2.13) ...

Selecting previously unselected package php8.1-readline.

Preparing to unpack .../35-php8.1-readline_8.1.2-1ubuntu2.13_amd64.deb ...

Unpacking php8.1-readline (8.1.2-1ubuntu2.13) ...

Selecting previously unselected package php8.1-cli.

Preparing to unpack .../36-php8.1-cli_8.1.2-1ubuntu2.13_amd64.deb ...

Unpacking php8.1-cli (8.1.2-1ubuntu2.13) ...

Selecting previously unselected package php8.1-fpm.

Preparing to unpack .../37-php8.1-fpm_8.1.2-1ubuntu2.13_amd64.deb ...

Unpacking php8.1-fpm (8.1.2-1ubuntu2.13) ...

Selecting previously unselected package php-fpm.

Preparing to unpack .../38-php-fpm_2%3a8.1+92ubuntu1_all.deb ...

Unpacking php-fpm (2:8.1+92ubuntu1) ...

Setting up libip4tc2:amd64 (1.8.7-1ubuntu5.1) ...

Setting up media-types (7.0.0) ...

Setting up libapparmor1:amd64 (3.0.4-2ubuntu2.2) ...

Setting up libsodium23:amd64 (1.0.18-1build2) ...

Setting up xdg-user-dirs (0.17-2ubuntu4) ...

Setting up libmagic-mgc (1:5.41-3) ...

Setting up psmisc (23.4-2build3) ...

Setting up libglib2.0-0:amd64 (2.72.4-0ubuntu2.2) ...

No schema files found: doing nothing.

Setting up libargon2-1:amd64 (0~20171227-0.3) ...

Setting up libedit2:amd64 (3.1-20210910-1build1) ...

Setting up libsqlite3-0:amd64 (3.37.2-2ubuntu0.1) ...

Setting up libmagic1:amd64 (1:5.41-3) ...

Setting up file (1:5.41-3) ...

Setting up perl-modules-5.34 (5.34.0-3ubuntu1.2) ...

Setting up bzip2 (1.0.8-5build1) ...

Setting up tzdata (2023c-0ubuntu0.22.04.2) ...

  

Current default time zone: 'Etc/UTC'

Local time is now:      Wed Jul 19 19:11:42 UTC 2023.

Universal Time is now:  Wed Jul 19 19:11:42 UTC 2023.

Run 'dpkg-reconfigure tzdata' if you wish to change it.

  

Setting up libglib2.0-data (2.72.4-0ubuntu2.2) ...

Setting up libdbus-1-3:amd64 (1.12.20-2ubuntu4.1) ...

Setting up dbus (1.12.20-2ubuntu4.1) ...

Setting up xz-utils (5.2.5-2ubuntu1) ...

update-alternatives: using /usr/bin/xz to provide /usr/bin/lzma (lzma) in auto mode

update-alternatives: warning: skip creation of /usr/share/man/man1/lzma.1.gz because associated file /usr/share/man/man1/xz.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/unlzma.1.gz because associated file /usr/share/man/man1/unxz.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzcat.1.gz because associated file /usr/share/man/man1/xzcat.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzmore.1.gz because associated file /usr/share/man/man1/xzmore.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzless.1.gz because associated file /usr/share/man/man1/xzless.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzdiff.1.gz because associated file /usr/share/man/man1/xzdiff.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzcmp.1.gz because associated file /usr/share/man/man1/xzcmp.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzgrep.1.gz because associated file /usr/share/man/man1/xzgrep.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzegrep.1.gz because associated file /usr/share/man/man1/xzegrep.1.gz (of link group lzma) doesn't exist

update-alternatives: warning: skip creation of /usr/share/man/man1/lzfgrep.1.gz because associated file /usr/share/man/man1/xzfgrep.1.gz (of link group lzma) doesn't exist

Setting up shared-mime-info (2.1-2) ...

Setting up libdevmapper1.02.1:amd64 (2:1.02.175-2.1ubuntu4) ...

Setting up dmsetup (2:1.02.175-2.1ubuntu4) ...

Setting up libmpdec3:amd64 (2.5.1-2build2) ...

Setting up libgirepository-1.0-1:amd64 (1.72.0-1) ...

Setting up netbase (6.3) ...

Setting up libjson-c5:amd64 (0.15-3~ubuntu1.22.04.1) ...

Setting up readline-common (8.1.2-1) ...

Setting up libkmod2:amd64 (29-1ubuntu1) ...

Setting up libgdbm6:amd64 (1.23-1) ...

Setting up php-common (2:92ubuntu1) ...

Created symlink /etc/systemd/system/timers.target.wants/phpsessionclean.timer → /lib/systemd/system/phpsessionclean.timer.

Setting up php8.1-common (8.1.2-1ubuntu2.13) ...

  

Creating config file /etc/php/8.1/mods-available/calendar.ini with new version

  

Creating config file /etc/php/8.1/mods-available/ctype.ini with new version

  

Creating config file /etc/php/8.1/mods-available/exif.ini with new version

  

Creating config file /etc/php/8.1/mods-available/fileinfo.ini with new version

  

Creating config file /etc/php/8.1/mods-available/ffi.ini with new version

  

Creating config file /etc/php/8.1/mods-available/ftp.ini with new version

  

Creating config file /etc/php/8.1/mods-available/gettext.ini with new version

  

Creating config file /etc/php/8.1/mods-available/iconv.ini with new version

  

Creating config file /etc/php/8.1/mods-available/pdo.ini with new version

  

Creating config file /etc/php/8.1/mods-available/phar.ini with new version

  

Creating config file /etc/php/8.1/mods-available/posix.ini with new version

  

Creating config file /etc/php/8.1/mods-available/shmop.ini with new version

  

Creating config file /etc/php/8.1/mods-available/sockets.ini with new version

  

Creating config file /etc/php/8.1/mods-available/sysvmsg.ini with new version

  

Creating config file /etc/php/8.1/mods-available/sysvsem.ini with new version

  

Creating config file /etc/php/8.1/mods-available/sysvshm.ini with new version

  

Creating config file /etc/php/8.1/mods-available/tokenizer.ini with new version

Setting up libreadline8:amd64 (8.1.2-1) ...

Setting up libpython3.10-stdlib:amd64 (3.10.6-1~22.04.2ubuntu1.1) ...

Setting up libgdbm-compat4:amd64 (1.23-1) ...

Setting up gir1.2-glib-2.0:amd64 (1.72.0-1) ...

Setting up libcryptsetup12:amd64 (2:2.4.3-1ubuntu1.1) ...

Setting up php8.1-readline (8.1.2-1ubuntu2.13) ...

  

Creating config file /etc/php/8.1/mods-available/readline.ini with new version

Setting up php8.1-opcache (8.1.2-1ubuntu2.13) ...

  

Creating config file /etc/php/8.1/mods-available/opcache.ini with new version

Setting up libpython3-stdlib:amd64 (3.10.6-1~22.04) ...

Setting up libperl5.34:amd64 (5.34.0-3ubuntu1.2) ...

Setting up python3.10 (3.10.6-1~22.04.2ubuntu1.1) ...

Setting up python3 (3.10.6-1~22.04) ...

Setting up systemd (249.11-0ubuntu3.9) ...

Created symlink /etc/systemd/system/getty.target.wants/getty@tty1.service → /lib/systemd/system/getty@.service.

Created symlink /etc/systemd/system/multi-user.target.wants/remote-fs.target → /lib/systemd/system/remote-fs.target.

Created symlink /etc/systemd/system/dbus-org.freedesktop.resolve1.service → /lib/systemd/system/systemd-resolved.service.

Created symlink /etc/systemd/system/multi-user.target.wants/systemd-resolved.service → /lib/systemd/system/systemd-resolved.service.

ln: failed to create symbolic link '/etc/resolv.conf': Device or resource busy

Created symlink /etc/systemd/system/sysinit.target.wants/systemd-pstore.service → /lib/systemd/system/systemd-pstore.service.

Initializing machine ID from D-Bus machine ID.

Setting up perl (5.34.0-3ubuntu1.2) ...

Setting up python3-gi (3.42.1-0ubuntu1) ...

Setting up systemd-timesyncd (249.11-0ubuntu3.9) ...

Created symlink /etc/systemd/system/dbus-org.freedesktop.timesync1.service → /lib/systemd/system/systemd-timesyncd.service.

Created symlink /etc/systemd/system/sysinit.target.wants/systemd-timesyncd.service → /lib/systemd/system/systemd-timesyncd.service.

Setting up mailcap (3.70+nmu1ubuntu1) ...

Setting up python3-dbus (1.2.18-3build1) ...

Setting up mime-support (3.66) ...

Setting up php8.1-cli (8.1.2-1ubuntu2.13) ...

update-alternatives: using /usr/bin/php8.1 to provide /usr/bin/php (php) in auto mode

update-alternatives: warning: skip creation of /usr/share/man/man1/php.1.gz because associated file /usr/share/man/man1/php8.1.1.gz (of link group php) doesn't exist

update-alternatives: using /usr/bin/phar8.1 to provide /usr/bin/phar (phar) in auto mode

update-alternatives: warning: skip creation of /usr/share/man/man1/phar.1.gz because associated file /usr/share/man/man1/phar8.1.1.gz (of link group phar) doesn't exist

update-alternatives: using /usr/bin/phar.phar8.1 to provide /usr/bin/phar.phar (phar.phar) in auto mode

update-alternatives: warning: skip creation of /usr/share/man/man1/phar.phar.1.gz because associated file /usr/share/man/man1/phar.phar8.1.1.gz (of link group phar.phar) doesn't exist

  

Creating config file /etc/php/8.1/cli/php.ini with new version

Setting up networkd-dispatcher (2.1-2ubuntu0.22.04.2) ...

Created symlink /etc/systemd/system/multi-user.target.wants/networkd-dispatcher.service → /lib/systemd/system/networkd-dispatcher.service.

Setting up php8.1-fpm (8.1.2-1ubuntu2.13) ...

  

Creating config file /etc/php/8.1/fpm/php.ini with new version

Created symlink /etc/systemd/system/multi-user.target.wants/php8.1-fpm.service → /lib/systemd/system/php8.1-fpm.service.

invoke-rc.d: could not determine current runlevel

invoke-rc.d: policy-rc.d denied execution of start.

Setting up php-fpm (2:8.1+92ubuntu1) ...

Processing triggers for libc-bin (2.35-0ubuntu3.1) ...

Processing triggers for php8.1-cli (8.1.2-1ubuntu2.13) ...

Processing triggers for php8.1-fpm (8.1.2-1ubuntu2.13) ...

invoke-rc.d: could not determine current runlevel

invoke-rc.d: policy-rc.d denied execution of restart.

Removing intermediate container 0c037cd35c5d

 ---> f8f94f585f20

Step 5/7 : VOLUME "/var/www/html"

 ---> Running in 3d65057634ca

Removing intermediate container 3d65057634ca

 ---> 9e53d1a420e4

Step 6/7 : EXPOSE 80

 ---> Running in d519b7fdb37c

Removing intermediate container d519b7fdb37c

 ---> 1e3644ace2a5

Step 7/7 : CMD /usr/sbin/nginx -g "daemon off;"

 ---> Running in 4cf8fbba05eb

Removing intermediate container 4cf8fbba05eb

 ---> 314f99acd889

Successfully built 314f99acd889

Successfully tagged test_image:latest

root@ubunto:~/mydocker# docker ps -a

CONTAINER ID   IMAGE     COMMAND       CREATED          STATUS                      PORTS     NAMES

bd1b54d99b21   ubuntu    "/bin/bash"   55 minutes ago   Exited (0) 55 minutes ago             nifty_moore

root@ubunto:~/mydocker# docker images

REPOSITORY   TAG       IMAGE ID       CREATED          SIZE

test_image   latest    314f99acd889   2 minutes ago    311MB

<none>       <none>    90d8937f31de   10 minutes ago   175MB

php          latest    4bf46c0328a4   8 days ago       529MB

nginx        latest    021283c8eb95   2 weeks ago      187MB

ubuntu       latest    5a81c4b8502e   3 weeks ago      77.8MB

root@ubunto:~/mydocker# docker run -d -p 9000:80 test_image

c95a5d793e9e996da007ffed86664cfac52ca6d4bdb2b0b6bf46db3766242246

root@ubunto:~/mydocker# docker ps -a

CONTAINER ID   IMAGE        COMMAND                  CREATED          STATUS                      PORTS                                   NAMES

c95a5d793e9e   test_image   "/bin/sh -c '/usr/sb…"   6 seconds ago    Up 5 seconds                0.0.0.0:9000->80/tcp, :::9000->80/tcp   reverent_pike

bd1b54d99b21   ubuntu       "/bin/bash"              57 minutes ago   Exited (0) 57 minutes ago                                           nifty_moore

root@ubunto:~/mydocker# docker stop c95a5d793e9e

c95a5d793e9e

root@ubunto:~/mydocker# docker ps -a

CONTAINER ID   IMAGE        COMMAND                  CREATED              STATUS                       PORTS     NAMES

c95a5d793e9e   test_image   "/bin/sh -c '/usr/sb…"   About a minute ago   Exited (137) 4 seconds ago             reverent_pike

bd1b54d99b21   ubuntu       "/bin/bash"              58 minutes ago       Exited (0) 58 minutes ago              nifty_moore

root@ubunto:~/mydocker#
```
