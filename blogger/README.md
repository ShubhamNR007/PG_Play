----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# blogger
# 3/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http

wpscan --url http://192.168.54.217/assets/fonts/blog/ --plugins-detection aggressive

postexploitation
vagrant:vagrant