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