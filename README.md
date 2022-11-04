# Test-GPS-Module

Hardware: 
GY-NEO6MV2 GPS Module, 
Raspberry Pi 4

Software:
Rasbian OS

Testing Steps:

1. Edit /boot/config.txt file

sudo nano /boot/config.txt

Append the follwing lines: 

dtparam=spi=on
dtoverlay=pi3-disable-bt
core_freq=250
enable_uart=1
force_turbo=1

2. Edit /boot/cmdline.txt file

Replace the contents to the follwing code:

dwc_otg.lpm_enable=0 console=tty1 root=/dev/mmcblk0p2 rootfstype=ext4 elevator=deadline fsck.repair=yes rootwait quiet splash plymouth.ignore-serial-consoles

3. Reboot Raspberry Pi

sudo reboot

4. Catch GPS NMEA data

sudo cat /dev/ttyAMA0
