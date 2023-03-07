----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# FunboxRookie
# 27/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT      STATE    SERVICE
21/tcp    open     ftp
22/tcp    open     ssh
80/tcp    open     http
4443/tcp  filtered pharos
27355/tcp filtered unknown


got robots.txt
logs/

can login ftp as anonymous
After download all zip files First we generate hash all files by using the zip2john tool. and we crack only two zip file cathrine.zip and tom.zip. let’s extract the zip file data After extract the file we found a private SSH key

catwoman         (cathrine.zip/id_rsa)     
iubire           (tom.zip/id_rsa)     


cat .mysql_history
insert\040into\040support\040(tom,\040xx11yy22!);

tom:xx11yy22!