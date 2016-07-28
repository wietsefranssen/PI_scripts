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

