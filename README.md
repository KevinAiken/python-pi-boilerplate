# python-pi-boilerplate
Personal starter for projects on Raspberry Pi's using Python

# Pi Setup
Download Raspbian: https://www.raspberrypi.org/downloads/raspbian/

`lsblk -p` to find your sd card's name (usually /dev/mmcblk0 or /dev/sdX)

Unmount it if it has been mounted: `umount /dev/sdX1` 

Unzip Raspbian and flash the card: `sudo dd bs=4M if=2020-02-13-raspbian-buster.img of=/dev/sdX status=progress conv=fsync`

Place this `wpa_supplicant.conf` in the boot folder (https://www.raspberrypi.org/documentation/configuration/wireless/headless.md): 
```ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=US

network={
 ssid="<Name of your WiFi>"
 psk="<Password for your WiFi>"
}
```

Place a file named `ssh` with no extension on the boot partition to enable ssh for headless usage: https://www.raspberrypi.org/documentation/remote-access/ssh/README.md

Boot the Pi.

`ssh pi@<ip>` and enter raspberry as the password.
