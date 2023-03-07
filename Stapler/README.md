----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# Stapler
# 18/2/2023

----------------------------------------------------
# users
----------------------------------------------------
Elly
Harry
John
kathy

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE     VERSION
21/tcp   open  ftp         vsftpd 2.0.8 or later
22/tcp   open  ssh         OpenSSH 7.2p2 Ubuntu 4 (Ubuntu Linux; protocol 2.0)
53/tcp   open  tcpwrapped
80/tcp   open  http        PHP cli server 5.5 or later
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
666/tcp  open  tcpwrapped
3306/tcp open  mysql       MySQL 5.7.12-0ubuntu1
12380

----------------------------------------------------
# ftp
----------------------------------------------------
ftp 192.168.107.148
anonymous
get note

----------------------------------------------------
# samba
----------------------------------------------------
smbclient -L //192.168.107.148 
        Sharename       Type      Comment
        ---------       ----      -------
        print$          Disk      Printer Drivers
        kathy           Disk      Fred, What are we doing here?
        tmp             Disk      All temporary files should be stored here
        IPC$            IPC       IPC Service (red server (Samba, Ubuntu))


-> enum4linux 192.168.107.148 
S-1-22-1-1000 Unix User\peter (Local User)
S-1-22-1-1001 Unix User\RNunemaker (Local User)
S-1-22-1-1002 Unix User\ETollefson (Local User)
S-1-22-1-1003 Unix User\DSwanger (Local User)
S-1-22-1-1004 Unix User\AParnell (Local User)
S-1-22-1-1005 Unix User\SHayslett (Local User)
S-1-22-1-1006 Unix User\MBassin (Local User)
S-1-22-1-1007 Unix User\JBare (Local User)
S-1-22-1-1008 Unix User\LSolum (Local User)
S-1-22-1-1009 Unix User\IChadwick (Local User)
S-1-22-1-1010 Unix User\MFrei (Local User)
S-1-22-1-1011 Unix User\SStroud (Local User)
S-1-22-1-1012 Unix User\CCeaser (Local User)
S-1-22-1-1013 Unix User\JKanode (Local User)
S-1-22-1-1014 Unix User\CJoo (Local User)
S-1-22-1-1015 Unix User\Eeth (Local User)
S-1-22-1-1016 Unix User\LSolum2 (Local User)
S-1-22-1-1017 Unix User\JLipps (Local User)
S-1-22-1-1018 Unix User\jamie (Local User)
S-1-22-1-1019 Unix User\Sam (Local User)
S-1-22-1-1020 Unix User\Drew (Local User)
S-1-22-1-1021 Unix User\jess (Local User)
S-1-22-1-1022 Unix User\SHAY (Local User)
S-1-22-1-1023 Unix User\Taylor (Local User)
S-1-22-1-1024 Unix User\mel (Local User)
S-1-22-1-1025 Unix User\kai (Local User)
S-1-22-1-1026 Unix User\zoe (Local User)
S-1-22-1-1027 Unix User\NATHAN (Local User)
S-1-22-1-1028 Unix User\www (Local User)
S-1-22-1-1029 Unix User\elly (Local User)

----------------------------------------------------
# DNS server
----------------------------------------------------
-> nslookup 192.168.107.148    
148.107.168.192.in-addr.arpa    name = 192.168.107.148.

----------------------------------------------------
# DOOM port 666
----------------------------------------------------
-> nc 192.168.107.148 666 > doom
-> file doom 
doom: Zip archive data, at least v2.0 to extract, compression method=deflate
-> strings message2.jpg 
JFIF
vPhotoshop 3.0
8BIM
1If you are reading this, you should get a cookie!
8BIM
$3br
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
        #3R
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
/<}m
>,xr?
u-o[
Sxw]
v;]>
|_m7
l~!|0
<Elu
I[[k:>
>5[^k
;o{o
>xgH
mCXi
PE<R"
umcV
g[Y@=
[\Y_
\Oku
'X|(
?=?i
//Do
1okb
,>,&
n<;oc
*?      xC
~ |y
6{M6
-

----------------------------------------------------
# gobuster http://192.168.107.148:12380 
----------------------------------------------------

When performing a gobuster scan against the target, it has found an /admin112233, a /blogblog and a /phpmyadmin entry:


