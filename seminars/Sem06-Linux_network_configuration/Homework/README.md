# Задача№1

> Настроить iptables: разрешить подключения только на 22-й и 80-й порты.  

```bash
root@ubunto:~# sudo iptables -L -v

Chain INPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

  

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

  

Chain OUTPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

root@ubunto:~# sudo iptables -A INPUT -i lo -j ACCEPT

root@ubunto:~# sudo iptables -L -v

Chain INPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

    0     0 ACCEPT     all  --  lo     any     anywhere             anywhere            

  

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

  

Chain OUTPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

root@ubunto:~# sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

root@ubunto:~# sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT

root@ubunto:~# sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT

root@ubunto:~# sudo iptables -L -v

Chain INPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

    0     0 ACCEPT     all  --  lo     any     anywhere             anywhere            

   26  1908 ACCEPT     tcp  --  any    any     anywhere             anywhere             tcp dpt:ssh

    0     0 ACCEPT     tcp  --  any    any     anywhere             anywhere             tcp dpt:http

    0     0 ACCEPT     tcp  --  any    any     anywhere             anywhere             tcp dpt:https

  

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

  

Chain OUTPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

root@ubunto:~# sudo iptables -A INPUT -j DROP

root@ubunto:~# sudo iptables -L -v

Chain INPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

    0     0 ACCEPT     all  --  lo     any     anywhere             anywhere            

   91  6764 ACCEPT     tcp  --  any    any     anywhere             anywhere             tcp dpt:ssh

    0     0 ACCEPT     tcp  --  any    any     anywhere             anywhere             tcp dpt:http

    0     0 ACCEPT     tcp  --  any    any     anywhere             anywhere             tcp dpt:https

    0     0 DROP       all  --  any    any     anywhere             anywhere            

  

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

  

Chain OUTPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

root@ubunto:~#
```

# Задача №2

> Настроить проброс портов локально с порта 80 на порт 8080.  

```bash
root@ubunto:~# iptables -t nat -I PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080         

root@ubunto:~# sudo iptables -L -t nat

Chain PREROUTING (policy ACCEPT)

target     prot opt source               destination         

REDIRECT   tcp  --  anywhere             anywhere             tcp dpt:http redir ports 8080

REDIRECT   tcp  --  anywhere             anywhere             tcp dpt:http redir ports 8080

  

Chain INPUT (policy ACCEPT)

target     prot opt source               destination         

  

Chain OUTPUT (policy ACCEPT)

target     prot opt source               destination         

  

Chain POSTROUTING (policy ACCEPT)

target     prot opt source               destination         

root@ubunto:~#
```

# Задача №3

> Запретить любой входящий трафик с IP-адреса 3.4.5.6.

```bash
root@ubunto:~# sudo iptables -A INPUT -p tcp -s 3.4.5.6 -j DROP

root@ubunto:~# sudo iptables -L -v

Chain INPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

    0     0 DROP       tcp  --  any    any     3.4.5.6              anywhere            

  

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

  

Chain OUTPUT (policy ACCEPT 0 packets, 0 bytes)

 pkts bytes target     prot opt in     out     source               destination         

root@ubunto:~#
```

# Задача №4

> Запустите mc. Используя ps, найдите PID процесса, завершите процесс, передав ему сигнал 9.

```bash
root@ubunto:~# mc

root@ubunto:~# ps aux | grep mc

root        2883  0.0  0.9  19288  9240 pts/0    S+   23:23   0:00 **mc**

root        2904  0.0  0.2   7004  2264 pts/1    S+   23:23   0:00 grep --color=auto **mc**

root@ubunto:~# kill -s 9 2883Killed

root@ubunto:~# ps aux | grep mc

root        2906  0.0  0.2   7004  2268 pts/0    S+   23:23   0:00 grep --color=auto **mc**

root@ubunto:~#
```
