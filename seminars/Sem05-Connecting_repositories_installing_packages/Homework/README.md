# Задача №1

> Подключить репозиторий с nginx любым удобным способом, установить nginx и потом удалить nginx, используя утилиту dpkg.


```bash
root@ubunto:~# sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C300EE8C

Warning: apt-key is deprecated. Manage keyring files in trusted.gpg.d instead (see apt-key(8)).

Executing: /tmp/apt-key-gpghome.BZZmBBJ1ri/gpg.1.sh --keyserver keyserver.ubuntu.com --recv-keys C300EE8C

gpg: key 00A6F0A3C300EE8C: "Launchpad Stable" not changed

gpg: Total number processed: 1

gpg:              unchanged: 1

root@ubunto:~# sudo echo "deb  http://ppa.launchpad.net/nginx/stable/ubuntu lucid main" >> /etc/apt/sources.list

root@ubunto:~# sudo apt update

Get:1 http://ppa.launchpad.net/nginx/stable/ubuntu lucid InRelease [14.3 kB]

Hit:2 http://archive.ubuntu.com/ubuntu jammy InRelease                                                                 

Hit:3 http://security.ubuntu.com/ubuntu jammy-security InRelease          

Err:1 http://ppa.launchpad.net/nginx/stable/ubuntu lucid InRelease        

  The following signatures were invalid: 8B3981E7A6852F782CC4951600A6F0A3C300EE8C

Hit:4 http://archive.ubuntu.com/ubuntu jammy-updates InRelease

Hit:5 http://archive.ubuntu.com/ubuntu jammy-backports InRelease

Reading package lists... Done

**W:** http://ppa.launchpad.net/nginx/stable/ubuntu/dists/lucid/InRelease: Key is stored in legacy trusted.gpg keyring (/etc/apt/trusted.gpg), see the DEPRECATION section in apt-key(8) for details.

**W:** GPG error: http://ppa.launchpad.net/nginx/stable/ubuntu lucid InRelease: The following signatures were invalid: 8B3981E7A6852F782CC4951600A6F0A3C300EE8C

**E:** The repository 'http://ppa.launchpad.net/nginx/stable/ubuntu lucid InRelease' is not signed.

N: Updating from such a repository can't be done securely, and is therefore disabled by default.

N: See apt-secure(8) manpage for repository creation and user configuration details.

root@ubunto:~# sudo apt install -y nginx

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

The following additional packages will be installed:

  libdeflate0 libgd3 libjbig0 libjpeg-turbo8 libjpeg8 libnginx-mod-http-geoip2 libnginx-mod-http-image-filter

  libnginx-mod-http-xslt-filter libnginx-mod-mail libnginx-mod-stream libnginx-mod-stream-geoip2 libtiff5 libwebp7

  libxpm4 nginx-common nginx-core

Suggested packages:

  libgd-tools fcgiwrap nginx-doc ssl-cert

The following NEW packages will be installed:

  libdeflate0 libgd3 libjbig0 libjpeg-turbo8 libjpeg8 libnginx-mod-http-geoip2 libnginx-mod-http-image-filter

  libnginx-mod-http-xslt-filter libnginx-mod-mail libnginx-mod-stream libnginx-mod-stream-geoip2 libtiff5 libwebp7

  libxpm4 nginx nginx-common nginx-core

0 upgraded, 17 newly installed, 0 to remove and 17 not upgraded.

Need to get 1488 kB of archives.

After this operation, 4795 kB of additional disk space will be used.

Get:1 http://archive.ubuntu.com/ubuntu jammy/main amd64 libdeflate0 amd64 1.10-2 [70.9 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy/main amd64 libjpeg-turbo8 amd64 2.1.2-0ubuntu1 [134 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy/main amd64 libjpeg8 amd64 8c-2ubuntu10 [2264 B]

Get:4 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libjbig0 amd64 2.1-3.1ubuntu0.22.04.1 [29.2 kB]

Get:5 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libwebp7 amd64 1.2.2-2ubuntu0.22.04.1 [206 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libtiff5 amd64 4.3.0-6ubuntu0.4 [183 kB]

Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libxpm4 amd64 1:3.5.12-1ubuntu0.22.04.1 [36.4 kB]

Get:8 http://archive.ubuntu.com/ubuntu jammy/main amd64 libgd3 amd64 2.3.0-2ubuntu2 [129 kB]

Get:9 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx-common all 1.18.0-6ubuntu14.4 [40.0 kB]

Get:10 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-geoip2 amd64 1.18.0-6ubuntu14.4 [11.9 kB]

Get:11 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-image-filter amd64 1.18.0-6ubuntu14.4 [15.4 kB]

Get:12 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-http-xslt-filter amd64 1.18.0-6ubuntu14.4 [13.7 kB]

Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-mail amd64 1.18.0-6ubuntu14.4 [45.7 kB]

Get:14 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-stream amd64 1.18.0-6ubuntu14.4 [72.9 kB]

Get:15 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libnginx-mod-stream-geoip2 amd64 1.18.0-6ubuntu14.4 [10.1 kB]

Get:16 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx-core amd64 1.18.0-6ubuntu14.4 [484 kB]

Get:17 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 nginx amd64 1.18.0-6ubuntu14.4 [3872 B]

Fetched 1488 kB in 2s (830 kB/s)

Preconfiguring packages ...

Selecting previously unselected package libdeflate0:amd64.

(Reading database ... 66641 files and directories currently installed.)

Preparing to unpack .../00-libdeflate0_1.10-2_amd64.deb ...

Unpacking libdeflate0:amd64 (1.10-2) ...

Selecting previously unselected package libjpeg-turbo8:amd64.

Preparing to unpack .../01-libjpeg-turbo8_2.1.2-0ubuntu1_amd64.deb ...

Unpacking libjpeg-turbo8:amd64 (2.1.2-0ubuntu1) ...

Selecting previously unselected package libjpeg8:amd64.

Preparing to unpack .../02-libjpeg8_8c-2ubuntu10_amd64.deb ...

Unpacking libjpeg8:amd64 (8c-2ubuntu10) ...

Selecting previously unselected package libjbig0:amd64.

Preparing to unpack .../03-libjbig0_2.1-3.1ubuntu0.22.04.1_amd64.deb ...

Unpacking libjbig0:amd64 (2.1-3.1ubuntu0.22.04.1) ...

Selecting previously unselected package libwebp7:amd64.

Preparing to unpack .../04-libwebp7_1.2.2-2ubuntu0.22.04.1_amd64.deb ...

Unpacking libwebp7:amd64 (1.2.2-2ubuntu0.22.04.1) ...

Selecting previously unselected package libtiff5:amd64.

Preparing to unpack .../05-libtiff5_4.3.0-6ubuntu0.4_amd64.deb ...

Unpacking libtiff5:amd64 (4.3.0-6ubuntu0.4) ...

Selecting previously unselected package libxpm4:amd64.

Preparing to unpack .../06-libxpm4_1%3a3.5.12-1ubuntu0.22.04.1_amd64.deb ...

Unpacking libxpm4:amd64 (1:3.5.12-1ubuntu0.22.04.1) ...

Selecting previously unselected package libgd3:amd64.

Preparing to unpack .../07-libgd3_2.3.0-2ubuntu2_amd64.deb ...

Unpacking libgd3:amd64 (2.3.0-2ubuntu2) ...

Selecting previously unselected package nginx-common.

Preparing to unpack .../08-nginx-common_1.18.0-6ubuntu14.4_all.deb ...

Unpacking nginx-common (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-geoip2.

Preparing to unpack .../09-libnginx-mod-http-geoip2_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-geoip2 (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-image-filter.

Preparing to unpack .../10-libnginx-mod-http-image-filter_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-image-filter (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-http-xslt-filter.

Preparing to unpack .../11-libnginx-mod-http-xslt-filter_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-http-xslt-filter (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-mail.

Preparing to unpack .../12-libnginx-mod-mail_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-mail (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-stream.

Preparing to unpack .../13-libnginx-mod-stream_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-stream (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package libnginx-mod-stream-geoip2.

Preparing to unpack .../14-libnginx-mod-stream-geoip2_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking libnginx-mod-stream-geoip2 (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package nginx-core.

Preparing to unpack .../15-nginx-core_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking nginx-core (1.18.0-6ubuntu14.4) ...

Selecting previously unselected package nginx.

Preparing to unpack .../16-nginx_1.18.0-6ubuntu14.4_amd64.deb ...

Unpacking nginx (1.18.0-6ubuntu14.4) ...

Setting up libxpm4:amd64 (1:3.5.12-1ubuntu0.22.04.1) ...

Setting up libdeflate0:amd64 (1.10-2) ...

Setting up nginx-common (1.18.0-6ubuntu14.4) ...

Created symlink /etc/systemd/system/multi-user.target.wants/nginx.service → /lib/systemd/system/nginx.service.

Setting up libjbig0:amd64 (2.1-3.1ubuntu0.22.04.1) ...

Setting up libnginx-mod-http-xslt-filter (1.18.0-6ubuntu14.4) ...

Setting up libjpeg-turbo8:amd64 (2.1.2-0ubuntu1) ...

Setting up libwebp7:amd64 (1.2.2-2ubuntu0.22.04.1) ...

Setting up libnginx-mod-http-geoip2 (1.18.0-6ubuntu14.4) ...

Setting up libjpeg8:amd64 (8c-2ubuntu10) ...

Setting up libnginx-mod-mail (1.18.0-6ubuntu14.4) ...

Setting up libnginx-mod-stream (1.18.0-6ubuntu14.4) ...

Setting up libtiff5:amd64 (4.3.0-6ubuntu0.4) ...

Setting up libnginx-mod-stream-geoip2 (1.18.0-6ubuntu14.4) ...

Setting up libgd3:amd64 (2.3.0-2ubuntu2) ...

Setting up libnginx-mod-http-image-filter (1.18.0-6ubuntu14.4) ...

Setting up nginx-core (1.18.0-6ubuntu14.4) ...

 * Upgrading binary nginx                                                                                        [ OK ] 

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

root@ubunto:~# dpkg -l nginx

Desired=Unknown/Install/Remove/Purge/Hold

| Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend

|/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)

||/ Name           Version            Architecture Description

+++-==============-==================-============-==========================================

ii  nginx          1.18.0-6ubuntu14.4 amd64        small, powerful, scalable web/proxy server

root@ubunto:~# sudo apt remove -y nginx

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

The following packages were automatically installed and are no longer required:

  libdeflate0 libgd3 libjbig0 libjpeg-turbo8 libjpeg8 libnginx-mod-http-geoip2 libnginx-mod-http-image-filter

  libnginx-mod-http-xslt-filter libnginx-mod-mail libnginx-mod-stream libnginx-mod-stream-geoip2 libtiff5 libwebp7

  libxpm4 nginx-common nginx-core

Use 'sudo apt autoremove' to remove them.

The following packages will be REMOVED:

  nginx

0 upgraded, 0 newly installed, 1 to remove and 17 not upgraded.

After this operation, 50.2 kB disk space will be freed.

(Reading database ... 66768 files and directories currently installed.)

Removing nginx (1.18.0-6ubuntu14.4) ...

root@ubunto:~# sudo dpkg -r nginx

**dpkg:** **warning:** ignoring request to remove nginx which isn't installed

root@ubunto:~# dpkg -l nginx

Desired=Unknown/Install/Remove/Purge/Hold

| Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend

|/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)

||/ Name           Version      Architecture Description

+++-==============-============-============-=================================

un  nginx          <none>       <none>       (no description available)
```

# Задача №2

> Установить пакет на свой выбор, используя snap.

```bash
root@ubunto:~# snap list

Name    Version        Rev    Tracking       Publisher   Notes

core20  20230622       1974   latest/stable  canonical✓  base

lxd     5.0.2-838e1b2  24322  5.0/stable/…   canonical✓  -

snapd   2.59.5         19457  latest/stable  canonical✓  snapd

root@ubunto:~# snap search vscode

Name                            Version        Publisher    Notes    Summary

code                            660393de       vscode✓      classic  Code editing. Redefined.

code-insiders                   48cd8e0c       vscode✓      classic  Code editing. Redefined.

vscode-html-languageserver      1.0.0          alexmurray✪  -        HTML Language Server extracted from VSCode

vscode-json-languageserver      1.3.4          alexmurray✪  -        JSON Language Server

vscode-markdown-languageserver  0.4.0-alpha.5  alexmurray✪  -        Markdown Language Server

karuta                          0.6.7          nekoaddict   -        Karuta is a scripting language for FPGA design (so called HLS).

awdur                           0.0.7          alcarney     -        Simple Screenwriting Application

code-tray                       1.0.0          devcass      -        Code Tray

root@ubunto:~# sudo snap install code

error: This revision of snap "code" was published using classic confinement and thus may perform

       arbitrary system changes outside of the security sandbox that snaps are usually confined to,

       which may put your system at risk.

  

       If you understand and want to proceed repeat the command including --classic.

root@ubunto:~# sudo snap install code --classic

code 660393de from Visual Studio Code (vscode✓) installed

root@ubunto:~# snap list

Name    Version        Rev    Tracking       Publisher   Notes

code    660393de       133    latest/stable  vscode✓     classic

core20  20230622       1974   latest/stable  canonical✓  base

lxd     5.0.2-838e1b2  24322  5.0/stable/…   canonical✓  -

snapd   2.59.5         19457  latest/stable  canonical✓  snapd

root@ubunto:~# code
```

# Задача №3

> Создать с помощью nano файл test.txt. Настроить автоматический бэкап этого файла раз в 10 минут в файл с названием test.txt.bak с использованием cron.

```bash
root@ubunto:~# mkdir bacups

root@ubunto:~# cd bacups/

root@ubunto:~/bacups# pwd

/root/bacups

root@ubunto:~/bacups# vim test

root@ubunto:~/bacups# ls

test

root@ubunto:~/bacups# crontab -e

no crontab for root - using an empty one

  

Select an editor.  To change later, run 'select-editor'.

  1. /bin/nano        <---- easiest

  2. /usr/bin/vim.basic

  3. /usr/bin/mcedit

  4. /usr/bin/vim.tiny

  5. /bin/ed

  

Choose 1-5 [1]: 2

crontab: installing new crontab

root@ubunto:~/bacups# ls -al

total 12

drwxr-xr-x 2 root root 4096 Jul 12 13:37 **.**

drwx------ 9 root root 4096 Jul 12 13:43 **..**

-rw-r--r-- 1 root root   15 Jul 12 13:37 test

root@ubunto:~/bacups# ls -al

total 12

drwxr-xr-x 2 root root 4096 Jul 12 13:37 **.**

drwx------ 9 root root 4096 Jul 12 13:43 **..**

-rw-r--r-- 1 root root   15 Jul 12 13:37 test

-rw-r--r-- 1 root root   15 Jul 12 13:49 test.bak

root@ubunto:~/bacups#
```

