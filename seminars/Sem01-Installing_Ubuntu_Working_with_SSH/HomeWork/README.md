```Bash
~/ ᐅ ssh-keygen -C root -f multipass-ssh-key

Generating public/private rsa key pair.

Enter passphrase (empty for no passphrase): 

Enter same passphrase again: 

Your identification has been saved in multipass-ssh-key

Your public key has been saved in multipass-ssh-key.pub

The key fingerprint is:

SHA256:M77umzjSlNvncS4E1nB2ISkMNLL74OKx56ALmbx2t8g root

The keys randomart image is:

+---[RSA 3072]----+

|    ..+o  ....   |

|     o .+ +..    |

|    .    * .     |

|     .  o .      |

|    o  oS.       |

|.o . oo. o.      |

|+.+ .o.o... .    |

|.+o*+.+..oo+     |

|+o+Eooo+*+...    |

+----[SHA256]-----+

~/ ᐅ touch cloud-init.yaml

~/ ᐅ vim multipass-ssh-key.pub

~/ ᐅ vim cloud-init.yaml      

~/ ᐅ multipass launch -n Ubunto --cloud-init cloud-init.yaml

Launched: Ubunto

~/ ᐅ multipass list

Name                    State             IPv4             Image

Ubunto                  Running           192.168.64.4     Ubuntu 22.04 LTS

~/ ᐅ multipass info Ubunto

Name:           Ubunto

State:          Running

IPv4:           192.168.64.4

Release:        Ubuntu 22.04.2 LTS

Image hash:     fe102bfb3d3d (Ubuntu 22.04 LTS)

CPU(s):         1

Load:           1.21 0.48 0.17

Disk usage:     1.4GiB out of 4.8GiB

Memory usage:   172.8MiB out of 951.5MiB

Mounts:         --

~/ ᐅ ssh vmuser@192.168.64.4 -i multipass-ssh-key -o StrictHostKeyChecking=no

Warning: Permanently added '192.168.64.4' (ED25519) to the list of known hosts.

Enter passphrase for key 'multipass-ssh-key': 

Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.15.0-75-generic x86_64)

  

 * Documentation:  https://help.ubuntu.com

 * Management:     https://landscape.canonical.com

 * Support:        https://ubuntu.com/advantage

  

  System information as of Wed Jun 21 01:54:09 MSK 2023

  

  System load:           0.16064453125

  Usage of /:            30.9% of 4.67GB

  Memory usage:          20%

  Swap usage:            0%

  Processes:             93

  Users logged in:       0

  IPv4 address for ens3: 192.168.64.4

  IPv6 address for ens3: fd1c:5fe9:1ec1:257f:5054:ff:fe4a:6184

  

  

Expanded Security Maintenance for Applications is not enabled.

  

0 updates can be applied immediately.

  

Enable ESM Apps to receive additional future security updates.

See https://ubuntu.com/esm or run: sudo pro status

  

  

  

The programs included with the Ubuntu system are free software;

the exact distribution terms for each program are described in the

individual files in /usr/share/doc/*/copyright.

  

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by

applicable law.

  

$ uname

Linux

$ uname -a

Linux Ubunto 5.15.0-75-generic #82-Ubuntu SMP Tue Jun 6 23:10:23 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux

$ hostnamectl

 Static hostname: Ubunto

       Icon name: computer-vm

         Chassis: vm

      Machine ID: 382c146724ed4746a0700847a06ffa2a

         Boot ID: 8b2237f7e4be4cf0b01a96cf53e892dd

  Virtualization: qemu

Operating System: Ubuntu 22.04.2 LTS               

          Kernel: Linux 5.15.0-75-generic

    Architecture: x86-64

 Hardware Vendor: QEMU

  Hardware Model: Standard PC _i440FX + PIIX, 1996_

$ sudo apt update

Hit:1 http://archive.ubuntu.com/ubuntu jammy InRelease

Get:2 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]

Get:3 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]             

Get:4 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [108 kB]             

Get:5 http://archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [14.1 MB]

Get:6 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [499 kB]

Get:7 http://security.ubuntu.com/ubuntu jammy-security/main Translation-en [129 kB]

Get:8 http://security.ubuntu.com/ubuntu jammy-security/main amd64 c-n-f Metadata [10.3 kB]     

Get:9 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [415 kB]          

Get:10 http://archive.ubuntu.com/ubuntu jammy/universe Translation-en [5652 kB]                 

Get:11 http://security.ubuntu.com/ubuntu jammy-security/restricted Translation-en [63.3 kB] 

Get:12 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [740 kB]           

Get:13 http://security.ubuntu.com/ubuntu jammy-security/universe Translation-en [131 kB]      

Get:14 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 c-n-f Metadata [15.6 kB]    

Get:15 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [30.2 kB]        

Get:16 http://archive.ubuntu.com/ubuntu jammy/universe amd64 c-n-f Metadata [286 kB]           

Get:17 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [217 kB]  

Get:18 http://security.ubuntu.com/ubuntu jammy-security/multiverse Translation-en [5828 B]

Get:19 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 c-n-f Metadata [252 B]  

Get:20 http://archive.ubuntu.com/ubuntu jammy/multiverse Translation-en [112 kB] 

Get:21 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 c-n-f Metadata [8372 B]

Get:22 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [721 kB]

Get:23 http://archive.ubuntu.com/ubuntu jammy-updates/main Translation-en [190 kB]

Get:24 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 c-n-f Metadata [15.3 kB]

Get:25 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [418 kB]

Get:26 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 c-n-f Metadata [604 B]

Get:27 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [932 kB]

Get:28 http://archive.ubuntu.com/ubuntu jammy-updates/universe Translation-en [199 kB]

Get:29 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 c-n-f Metadata [20.5 kB]

Get:30 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [35.3 kB]

Get:31 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse Translation-en [8452 B]

Get:32 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 c-n-f Metadata [468 B]

Get:33 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [40.9 kB]

Get:34 http://archive.ubuntu.com/ubuntu jammy-backports/main Translation-en [10.2 kB]

Get:35 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 c-n-f Metadata [388 B]

Get:36 http://archive.ubuntu.com/ubuntu jammy-backports/restricted amd64 c-n-f Metadata [116 B]

Get:37 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [23.4 kB]

Get:38 http://archive.ubuntu.com/ubuntu jammy-backports/universe Translation-en [15.0 kB]

Get:39 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 c-n-f Metadata [548 B]

Get:40 http://archive.ubuntu.com/ubuntu jammy-backports/multiverse amd64 c-n-f Metadata [116 B]

Fetched 25.4 MB in 6s (4115 kB/s)                                                                  

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

All packages are up to date.

$ sudo apt install mc

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

The following additional packages will be installed:

  bzip2 libssh2-1 mailcap mc-data mime-support unzip

Suggested packages:

  bzip2-doc arj catdvi | texlive-binaries dbview djvulibre-bin epub-utils genisoimage gv

  imagemagick libaspell-dev links | w3m | lynx odt2txt poppler-utils python python-boto python-tz

  unar wimtools xpdf | pdf-viewer zip

The following NEW packages will be installed:

  bzip2 libssh2-1 mailcap mc mc-data mime-support unzip

0 upgraded, 7 newly installed, 0 to remove and 0 not upgraded.

Need to get 2321 kB of archives.

After this operation, 8819 kB of additional disk space will be used.

Do you want to continue? [Y/n] y

Get:1 http://archive.ubuntu.com/ubuntu jammy/main amd64 bzip2 amd64 1.0.8-5build1 [34.8 kB]

Get:2 http://archive.ubuntu.com/ubuntu jammy/universe amd64 libssh2-1 amd64 1.10.0-3 [109 kB]

Get:3 http://archive.ubuntu.com/ubuntu jammy/main amd64 mailcap all 3.70+nmu1ubuntu1 [23.8 kB]

Get:4 http://archive.ubuntu.com/ubuntu jammy/universe amd64 mc-data all 3:4.8.27-1 [1427 kB]

Get:5 http://archive.ubuntu.com/ubuntu jammy/universe amd64 mc amd64 3:4.8.27-1 [547 kB]

Get:6 http://archive.ubuntu.com/ubuntu jammy/main amd64 mime-support all 3.66 [3696 B]

Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 unzip amd64 6.0-26ubuntu3.1 [174 kB]

Fetched 2321 kB in 2s (1386 kB/s)

Selecting previously unselected package bzip2.

(Reading database ... 64231 files and directories currently installed.)

Preparing to unpack .../0-bzip2_1.0.8-5build1_amd64.deb ...

Unpacking bzip2 (1.0.8-5build1) ...

Selecting previously unselected package libssh2-1:amd64.

Preparing to unpack .../1-libssh2-1_1.10.0-3_amd64.deb ...

Unpacking libssh2-1:amd64 (1.10.0-3) ...

Selecting previously unselected package mailcap.

Preparing to unpack .../2-mailcap_3.70+nmu1ubuntu1_all.deb ...

Unpacking mailcap (3.70+nmu1ubuntu1) ...

Selecting previously unselected package mc-data.

Preparing to unpack .../3-mc-data_3%3a4.8.27-1_all.deb ...

Unpacking mc-data (3:4.8.27-1) ...

Selecting previously unselected package mc.

Preparing to unpack .../4-mc_3%3a4.8.27-1_amd64.deb ...

Unpacking mc (3:4.8.27-1) ...

Selecting previously unselected package mime-support.

Preparing to unpack .../5-mime-support_3.66_all.deb ...

Unpacking mime-support (3.66) ...

Selecting previously unselected package unzip.

Preparing to unpack .../6-unzip_6.0-26ubuntu3.1_amd64.deb ...

Unpacking unzip (6.0-26ubuntu3.1) ...

Setting up unzip (6.0-26ubuntu3.1) ...

Setting up bzip2 (1.0.8-5build1) ...

Setting up mc-data (3:4.8.27-1) ...

Setting up libssh2-1:amd64 (1.10.0-3) ...

Setting up mailcap (3.70+nmu1ubuntu1) ...

Setting up mime-support (3.66) ...

Setting up mc (3:4.8.27-1) ...

Processing triggers for man-db (2.10.2-1) ...

Processing triggers for libc-bin (2.35-0ubuntu3.1) ...

Scanning processes...                                                                               

Scanning linux images...                                                                            

  

Running kernel seems to be up-to-date.

  

No services need to be restarted.

  

No containers need to be restarted.

  

No user sessions are running outdated binaries.

  

No VM guests are running outdated hypervisor (qemu) binaries on this host.

$ mc

  

$ lsb_release -a

No LSB modules are available.

Distributor ID: Ubuntu

Description: Ubuntu 22.04.2 LTS

Release: 22.04

Codename: jammy

```
