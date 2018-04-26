# rpi-notes
Raspberry Pi notes. Currently I'm using v2 of Pi and Raspbian Stretch Lite downloaded here: https://www.raspberrypi.org/downloads/raspbian/

## SSH
```
systemctl start ssh
systemctl enable ssh
```

## Dependencies
```
apt-get install git apache2 php libapache2-mod-php
```

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

## Pi Cam Software

```
cd
mkdir projects
cd projects
git clone https://github.com/silvanmelchior/RPi_Cam_Web_Interface.git
cd RPi_Cam_Web_Interface
sudo ./install.sh
```
