# rpi-notes
Raspberry Pi notes

## Wifi Setup for WPA2/AES

`/etc/network/interfaces`
```
# Include files from /etc/network/interfaces.d:
source-directory /etc/network/interfaces.d

auto lo
iface lo inet loopback

allow-hotplug wlan0
iface wlan0 inet manual 
wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```

`/etc/wpa_supplicant/wpa_supplicant.conf`
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=US

network={
    ssid="MYSSID"
    psk="MYPASS"
    proto=RSN
    key_mgmt=WPA-PSK
    pairwise=CCMP
    group=CCMP
    auth_alg=OPEN
}

```
