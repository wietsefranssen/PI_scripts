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

### Install openssh
Install openssh in order to do the rest of the steps remotely
```{r, engine='bash', count_lines}
sudo apt-get install openssh
```
