# dloader
This is a host tool, provide firmware download function through serial port.

# Usage:
sudo ./DLoader -pac <pac-path> -dev <dev-path> -baud <baud-rate> [-reset] [-nvbk false|true] [-filebk false|true] [-auto] [<-phasecheck> [-SN sn]] [-KeepCharge] [-PowerOff]

e.g.

sudo ./DLoader -pac /tmp/a.pac -dev /dev/ttyUSB0 -baud 460800 [-reset] [-nvbk false|true]

1. Input 'q' or 'Q' to stop download.
2. Open log:
  Detail data log: set the level to 6 in channel.ini
  App log: set the bellow in the BMTimeout.ini
  [Log]
  Enable = 1
  EnableFrameLog=1
3. -reset       reboot device after download
4. -nvbk        false: don't backup nv,     true: backup nv;    default backup nv
5. -filebk      false: don't backup file,   true: backup file;  default backup the specified partition.
6. -auto        used in auto download, need to power on device,dloader will auto send entry command to device,then device will auto entry download mode.
7. -phasecheck  auto write phasecheck and random generation sn,-SN :user can assign a sn.
8. -KeepCharge  support usb power supply
9. -PowerOff    PowerOff device after download
