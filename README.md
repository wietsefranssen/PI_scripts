# PI_scripts

## How to make a Time Capsule server for OS-X Time Machine

### Install `NOOBS` and `raspbian` first
(I tested it with: `NOOBS_v1.9.3.zip`)

#### Download and unzip
Download `NOOBS` at: https://downloads.raspberrypi.org/NOOBS_latest
And unzip it

Command line:
```{r, engine='bash', count_lines}
wget "http://director.downloads.raspberrypi.org/NOOBS/images/NOOBS-2016-05-31/NOOBS_v1_9_2.zip"
unzip ./NOOBS_v1_9_2.zip
```

#### Format SD and copy to SD
format the SD-card. Eg with `SDFormatter`: https://www.sdcard.org/downloads/formatter_4/

now copy all the contents of the `NOOBS` folder into the root of the SD-card.

#### Install raspbian
now just put the sd-card into the raspberry-pi and turn in on.

After waiting a while you get the option to install `Raspbian`. Just do that and wait again.

`Raspbian` should be installed now

#### Install raspbian lite
on OSX:
```
diskutil unmountDisk /dev/disk2
sudo dd bs=1m if=./Downloads/2016-05-27-raspbian-jessie-lite.img of=/dev/rdisk2
sync
```
(see also https://www.raspberrypi.org/documentation/installation/installing-images/linux.md)

### Install openssh (maybe not needed)
Install openssh on the PI in order to do the rest of the steps remotely
```{r, engine='bash', count_lines}
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install openssh-server
```

figure out the IP adress of the PI:
```{r, engine='bash', count_lines}
ifconfig
```
or look at first login screen!

login from the laptop with:
```{r, engine='bash', count_lines}
ssh pi@<IP-OF-PI>
```
(password is `raspbian` or `raspberry`)

### Update everything
```{r, engine='bash', count_lines}
sudo apt-get update
sudo apt-get upgrade
sudo apt-get clean
```

### raspi-config
Configure your internationalization settings which include language, keyboard layout, and regional settings.
```
sudo raspi-config
```

#### reboot:
```
sudo reboot
```

### Netatalk installation
see: http://netatalk.sourceforge.net/wiki/index.php/Install_Netatalk_3.1.9_on_Debian_8_Jessie


### HFS
```
sudo apt-get install hfsprogs hfsutils hfsplus
```
###
from: https://ubuntuforums.org/showthread.php?t=2105755
```
sudo apt-get install libc6-dev avahi-daemon libnss-mdns
```


```
<?xml version="1.0" standalone='no'?><!--*-nxml-*-->
<!DOCTYPE service-group SYSTEM "avahi-service.dtd">
<service-group>
    <name replace-wildcards="yes">%h</name>
    <service>
        <type>_afpovertcp._tcp</type>
        <port>548</port>
    </service>
    <service>
        <type>_device-info._tcp</type>
        <port>0</port>
        <txt-record>model=TimeCapsule</txt-record>
    </service>
</service-group>
```


