1. Управление пользователями:
	- создать нового пользователя;
	- убедиться, что информация о нем появилась в соответствующих файлах в системе;
	- удалить созданного пользователя;

```bash
root@ubunto:/etc# sudo useradd -m -s /bin/bash guest

root@ubunto:/etc# sudo passwd guest

New password: 

Retype new password: 

passwd: password updated successfully

root@ubunto:/etc# cat passwd

root:x:0:0:root:/root:/bin/bash

daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:x:3:3:sys:/dev:/usr/sbin/nologin

sync:x:4:65534:sync:/bin:/bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

man:x:6:12:man:/var/cache/man:/usr/sbin/nologin

lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

news:x:9:9:news:/var/spool/news:/usr/sbin/nologin

uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin

backup:x:34:34:backup:/var/backups:/usr/sbin/nologin

list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin

irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin

gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin

nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin

systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin

systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin

messagebus:x:102:105::/nonexistent:/usr/sbin/nologin

systemd-timesync:x:103:106:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin

syslog:x:104:111::/home/syslog:/usr/sbin/nologin

_apt:x:105:65534::/nonexistent:/usr/sbin/nologin

tss:x:106:112:TPM software stack,,,:/var/lib/tpm:/bin/false

uuidd:x:107:113::/run/uuidd:/usr/sbin/nologin

tcpdump:x:108:114::/nonexistent:/usr/sbin/nologin

sshd:x:109:65534::/run/sshd:/usr/sbin/nologin

pollinate:x:110:1::/var/cache/pollinate:/bin/false

landscape:x:111:116::/var/lib/landscape:/usr/sbin/nologin

fwupd-refresh:x:112:117:fwupd-refresh user,,,:/run/systemd:/usr/sbin/nologin

ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false

guest:x:1001:1001::/home/guest:/bin/bash

root@ubunto:/etc# su guest

**guest@ubunto**:**/etc**$ whoami

guest

**guest@ubunto**:**/etc**$ cd ~

**guest@ubunto**:**~**$ ls -al

total 20

drwxr-x--- 2 guest guest 4096 Jul  1 15:59 **.**

drwxr-xr-x 4 root  root  4096 Jul  1 15:59 **..**

-rw-r--r-- 1 guest guest  220 Jan  6  2022 .bash_logout

-rw-r--r-- 1 guest guest 3771 Jan  6  2022 .bashrc

-rw-r--r-- 1 guest guest  807 Jan  6  2022 .profile

**guest@ubunto**:**~**$ cd ..

**guest@ubunto**:**/home**$ ls -al

total 16

drwxr-xr-x  4 root   root   4096 Jul  1 15:59 **.**

drwxr-xr-x 20 root   root   4096 Jul  1 14:22 **..**

drwxr-x---  2 guest  guest  4096 Jul  1 15:59 **guest**

drwxr-x---  4 ubuntu ubuntu 4096 Jun 23 22:11 **ubuntu**

**guest@ubunto**:**/home**$ exit

exit

root@ubunto:/etc# sudo userdel -f guest

root@ubunto:/etc# cat passwd

root:x:0:0:root:/root:/bin/bash

daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:x:3:3:sys:/dev:/usr/sbin/nologin

sync:x:4:65534:sync:/bin:/bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

man:x:6:12:man:/var/cache/man:/usr/sbin/nologin

lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

news:x:9:9:news:/var/spool/news:/usr/sbin/nologin

uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin

backup:x:34:34:backup:/var/backups:/usr/sbin/nologin

list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin

irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin

gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin

nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin

systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin

systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin

messagebus:x:102:105::/nonexistent:/usr/sbin/nologin

systemd-timesync:x:103:106:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin

syslog:x:104:111::/home/syslog:/usr/sbin/nologin

_apt:x:105:65534::/nonexistent:/usr/sbin/nologin

tss:x:106:112:TPM software stack,,,:/var/lib/tpm:/bin/false

uuidd:x:107:113::/run/uuidd:/usr/sbin/nologin

tcpdump:x:108:114::/nonexistent:/usr/sbin/nologin

sshd:x:109:65534::/run/sshd:/usr/sbin/nologin

pollinate:x:110:1::/var/cache/pollinate:/bin/false

landscape:x:111:116::/var/lib/landscape:/usr/sbin/nologin

fwupd-refresh:x:112:117:fwupd-refresh user,,,:/run/systemd:/usr/sbin/nologin

ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false

root@ubunto:/etc# cd ~

root@ubunto:~# cd ..

root@ubunto:/# ls -al

total 76

drwxr-xr-x  20 root root  4096 Jul  1 14:22 **.**

drwxr-xr-x  20 root root  4096 Jul  1 14:22 **..**

lrwxrwxrwx   1 root root     7 Jun 16 05:07 **bin** -> **usr/bin**

drwxr-xr-x   4 root root  4096 Jun 16 05:10 **boot**

drwxr-xr-x  16 root root  3880 Jul  1 14:22 **dev**

drwxr-xr-x  95 root root  4096 Jul  1 16:14 **etc**

drwxr-xr-x   4 root root  4096 Jul  1 15:59 **home**

lrwxrwxrwx   1 root root     7 Jun 16 05:07 **lib** -> **usr/lib**

lrwxrwxrwx   1 root root     9 Jun 16 05:07 **lib32** -> **usr/lib32**

lrwxrwxrwx   1 root root     9 Jun 16 05:07 **lib64** -> **usr/lib64**

lrwxrwxrwx   1 root root    10 Jun 16 05:07 **libx32** -> **usr/libx32**

drwx------   2 root root 16384 Jun 16 05:09 **lost+found**

drwxr-xr-x   2 root root  4096 Jun 16 05:07 **media**

drwxr-xr-x   2 root root  4096 Jun 16 05:07 **mnt**

drwxr-xr-x   2 root root  4096 Jun 16 05:07 **opt**

drwxr-xr-x   4 root root  4096 Jun 23 22:18 **plugins**

dr-xr-xr-x 148 root root     0 Jul  1 14:22 **proc**

drwx------   8 root root  4096 Jul  1 15:58 **root**

drwxr-xr-x  28 root root   840 Jul  1 14:26 **run**

lrwxrwxrwx   1 root root     8 Jun 16 05:07 **sbin** -> **usr/sbin**

drwxr-xr-x   6 root root  4096 Jun 16 05:09 **snap**

drwxr-xr-x   2 root root  4096 Jun 16 05:07 **srv**

dr-xr-xr-x  13 root root     0 Jul  1 14:22 **sys**

drwxrwxrwt  11 root root  4096 Jul  1 14:28 tmp

drwxr-xr-x  14 root root  4096 Jun 16 05:07 **usr**

drwxr-xr-x  13 root root  4096 Jun 16 05:09 **var**

root@ubunto:/# cd home

root@ubunto:/home# ls -al

total 16

drwxr-xr-x  4 root   root   4096 Jul  1 15:59 **.**

drwxr-xr-x 20 root   root   4096 Jul  1 14:22 **..**

drwxr-x---  2   1001   1001 4096 Jul  1 16:14 **guest**

drwxr-x---  4 ubuntu ubuntu 4096 Jun 23 22:11 **ubuntu**

root@ubunto:/home# sudo rm -r guest

root@ubunto:/home# ls -al

total 12

drwxr-xr-x  3 root   root   4096 Jul  1 16:16 **.**

drwxr-xr-x 20 root   root   4096 Jul  1 14:22 **..**

drwxr-x---  4 ubuntu ubuntu 4096 Jun 23 22:11 **ubuntu**

root@ubunto:/home#
```


2. Управление группами:
	- создать группу;
	- попрактиковаться в смене групп у пользователей;
	- добавить пользователя в группу, не меняя основной;
	- удалить пользователя из группы.

```bash
root@ubunto:/home# sudo useradd -m -s /bin/bash user1

total 28

drwxr-xr-x  7 root   root   4096 Jul  1 16:23 **.**

drwxr-xr-x 20 root   root   4096 Jul  1 14:22 **..**

drwxr-x---  4 ubuntu ubuntu 4096 Jun 23 22:11 **ubuntu**

drwxr-x---  2 user1  user1  4096 Jul  1 16:23 **user1**

root@ubunto:/home# cd ..

root@ubunto:/# cd etc/

root@ubunto:/etc# cat passwd

root:x:0:0:root:/root:/bin/bash

daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:x:3:3:sys:/dev:/usr/sbin/nologin

sync:x:4:65534:sync:/bin:/bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

man:x:6:12:man:/var/cache/man:/usr/sbin/nologin

lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

news:x:9:9:news:/var/spool/news:/usr/sbin/nologin

uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin

backup:x:34:34:backup:/var/backups:/usr/sbin/nologin

list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin

irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin

gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin

nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin

systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin

systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin

messagebus:x:102:105::/nonexistent:/usr/sbin/nologin

systemd-timesync:x:103:106:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin

syslog:x:104:111::/home/syslog:/usr/sbin/nologin

_apt:x:105:65534::/nonexistent:/usr/sbin/nologin

tss:x:106:112:TPM software stack,,,:/var/lib/tpm:/bin/false

uuidd:x:107:113::/run/uuidd:/usr/sbin/nologin

tcpdump:x:108:114::/nonexistent:/usr/sbin/nologin

sshd:x:109:65534::/run/sshd:/usr/sbin/nologin

pollinate:x:110:1::/var/cache/pollinate:/bin/false

landscape:x:111:116::/var/lib/landscape:/usr/sbin/nologin

fwupd-refresh:x:112:117:fwupd-refresh user,,,:/run/systemd:/usr/sbin/nologin

ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false

user1:x:1001:1001::/home/user1:/bin/bash

root@ubunto:/etc# cd ~

root@ubunto:~# groupadd testgroup

root@ubunto:~# usermod -aG testgroup user1

root@ubunto:~# cd ..

root@ubunto:/# cd etc/

root@ubunto:/etc# cat group

root:x:0:

daemon:x:1:

bin:x:2:

sys:x:3:

adm:x:4:syslog,ubuntu

tty:x:5:

disk:x:6:

lp:x:7:

mail:x:8:

news:x:9:

uucp:x:10:

man:x:12:

proxy:x:13:

kmem:x:15:

dialout:x:20:ubuntu

fax:x:21:

voice:x:22:

cdrom:x:24:ubuntu

floppy:x:25:ubuntu

tape:x:26:

sudo:x:27:ubuntu

audio:x:29:ubuntu

dip:x:30:ubuntu

www-data:x:33:

backup:x:34:

operator:x:37:

list:x:38:

irc:x:39:

src:x:40:

gnats:x:41:

shadow:x:42:

utmp:x:43:

video:x:44:ubuntu

sasl:x:45:

plugdev:x:46:ubuntu

staff:x:50:

games:x:60:

users:x:100:

nogroup:x:65534:

systemd-journal:x:101:

systemd-network:x:102:

systemd-resolve:x:103:

crontab:x:104:

messagebus:x:105:

systemd-timesync:x:106:

input:x:107:

sgx:x:108:

kvm:x:109:

render:x:110:

syslog:x:111:

tss:x:112:

uuidd:x:113:

tcpdump:x:114:

_ssh:x:115:

landscape:x:116:

fwupd-refresh:x:117:

admin:x:118:

netdev:x:119:ubuntu

lxd:x:120:ubuntu

ubuntu:x:1000:

user1:x:1001:

testgroup:x:1005:user1

root@ubunto:/etc# cat passwd

root:x:0:0:root:/root:/bin/bash

daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:x:3:3:sys:/dev:/usr/sbin/nologin

sync:x:4:65534:sync:/bin:/bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

man:x:6:12:man:/var/cache/man:/usr/sbin/nologin

lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

news:x:9:9:news:/var/spool/news:/usr/sbin/nologin

uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin

backup:x:34:34:backup:/var/backups:/usr/sbin/nologin

list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin

irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin

gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin

nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin

systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin

systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin

messagebus:x:102:105::/nonexistent:/usr/sbin/nologin

systemd-timesync:x:103:106:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin

syslog:x:104:111::/home/syslog:/usr/sbin/nologin

_apt:x:105:65534::/nonexistent:/usr/sbin/nologin

tss:x:106:112:TPM software stack,,,:/var/lib/tpm:/bin/false

uuidd:x:107:113::/run/uuidd:/usr/sbin/nologin

tcpdump:x:108:114::/nonexistent:/usr/sbin/nologin

sshd:x:109:65534::/run/sshd:/usr/sbin/nologin

pollinate:x:110:1::/var/cache/pollinate:/bin/false

landscape:x:111:116::/var/lib/landscape:/usr/sbin/nologin

fwupd-refresh:x:112:117:fwupd-refresh user,,,:/run/systemd:/usr/sbin/nologin

ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false

user1:x:1001:1001::/home/user1:/bin/bash

root@ubunto:/etc# usermod --help

Usage: usermod [options] LOGIN

  

Options:

  -b, --badnames                allow bad names

  -c, --comment COMMENT         new value of the GECOS field

  -d, --home HOME_DIR           new home directory for the user account

  -e, --expiredate EXPIRE_DATE  set account expiration date to EXPIRE_DATE

  -f, --inactive INACTIVE       set password inactive after expiration

                                to INACTIVE

  -g, --gid GROUP               force use GROUP as new primary group

  -G, --groups GROUPS           new list of supplementary GROUPS

  -a, --append                  append the user to the supplemental GROUPS

                                mentioned by the -G option without removing

                                the user from other groups

  -h, --help                    display this help message and exit

  -l, --login NEW_LOGIN         new value of the login name

  -L, --lock                    lock the user account

  -m, --move-home               move contents of the home directory to the

                                new location (use only with -d)

  -o, --non-unique              allow using duplicate (non-unique) UID

  -p, --password PASSWORD       use encrypted password for the new password

  -R, --root CHROOT_DIR         directory to chroot into

  -P, --prefix PREFIX_DIR       prefix directory where are located the /etc/* files

  -s, --shell SHELL             new login shell for the user account

  -u, --uid UID                 new UID for the user account

  -U, --unlock                  unlock the user account

  -v, --add-subuids FIRST-LAST  add range of subordinate uids

  -V, --del-subuids FIRST-LAST  remove range of subordinate uids

  -w, --add-subgids FIRST-LAST  add range of subordinate gids

  -W, --del-subgids FIRST-LAST  remove range of subordinate gids

  -Z, --selinux-user SEUSER     new SELinux user mapping for the user account

  

root@ubunto:/etc# usermod -aG '' user1

root@ubunto:/etc# cat group

root:x:0:

daemon:x:1:

bin:x:2:

sys:x:3:

adm:x:4:syslog,ubuntu

tty:x:5:

disk:x:6:

lp:x:7:

mail:x:8:

news:x:9:

uucp:x:10:

man:x:12:

proxy:x:13:

kmem:x:15:

dialout:x:20:ubuntu

fax:x:21:

voice:x:22:

cdrom:x:24:ubuntu

floppy:x:25:ubuntu

tape:x:26:

sudo:x:27:ubuntu

audio:x:29:ubuntu

dip:x:30:ubuntu

www-data:x:33:

backup:x:34:

operator:x:37:

list:x:38:

irc:x:39:

src:x:40:

gnats:x:41:

shadow:x:42:

utmp:x:43:

video:x:44:ubuntu

sasl:x:45:

plugdev:x:46:ubuntu

staff:x:50:

games:x:60:

users:x:100:

nogroup:x:65534:

systemd-journal:x:101:

systemd-network:x:102:

systemd-resolve:x:103:

crontab:x:104:

messagebus:x:105:

systemd-timesync:x:106:

input:x:107:

sgx:x:108:

kvm:x:109:

render:x:110:

syslog:x:111:

tss:x:112:

uuidd:x:113:

tcpdump:x:114:

_ssh:x:115:

landscape:x:116:

fwupd-refresh:x:117:

admin:x:118:

netdev:x:119:ubuntu

lxd:x:120:ubuntu

ubuntu:x:1000:

user1:x:1001:

testgroup:x:1005:user1

root@ubunto:/etc# sudo gpasswd -d user1 testgroup

Removing user user1 from group testgroup

root@ubunto:/etc# cat group

root:x:0:

daemon:x:1:

bin:x:2:

sys:x:3:

adm:x:4:syslog,ubuntu

tty:x:5:

disk:x:6:

lp:x:7:

mail:x:8:

news:x:9:

uucp:x:10:

man:x:12:

proxy:x:13:

kmem:x:15:

dialout:x:20:ubuntu

fax:x:21:

voice:x:22:

cdrom:x:24:ubuntu

floppy:x:25:ubuntu

tape:x:26:

sudo:x:27:ubuntu

audio:x:29:ubuntu

dip:x:30:ubuntu

www-data:x:33:

backup:x:34:

operator:x:37:

list:x:38:

irc:x:39:

src:x:40:

gnats:x:41:

shadow:x:42:

utmp:x:43:

video:x:44:ubuntu

sasl:x:45:

plugdev:x:46:ubuntu

staff:x:50:

games:x:60:

users:x:100:

nogroup:x:65534:

systemd-journal:x:101:

systemd-network:x:102:

systemd-resolve:x:103:

crontab:x:104:

messagebus:x:105:

systemd-timesync:x:106:

input:x:107:

sgx:x:108:

kvm:x:109:

render:x:110:

syslog:x:111:

tss:x:112:

uuidd:x:113:

tcpdump:x:114:

_ssh:x:115:

landscape:x:116:

fwupd-refresh:x:117:

admin:x:118:

netdev:x:119:ubuntu

lxd:x:120:ubuntu

ubuntu:x:1000:

user1:x:1001:

user2:x:1002:

user3:x:1003:

user4:x:1004:

testgroup:x:1005:

root@ubunto:/etc#
```

3. Работа с группами.
	- Создать пользователя с правами суперпользователя. Проверить результат.
	- * Создать группу developer и нескольких пользователей, входящих в неё. Создать директорию для совместной работы. Сделать так, чтобы созданные одними пользователями файлы могли изменять другие пользователи этой группы.
	* * Создать в директории для совместной работы поддиректорию для обмена файлами, но чтобы удалять файлы могли только их создатели.

```bash
root@ubunto:/home# sudo useradd superuser

root@ubunto:/home# sudo usermod -G sudo superuser

root@ubunto:/home# su superuser

$ whoami

superuser

$ exit

root@ubunto:/home# 
```
