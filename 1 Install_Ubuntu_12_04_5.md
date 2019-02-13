# Install Ubuntu 12.04.5

[Download Ubuntu 32bit](http://releases.ubuntu.com/precise/)

## create USB Stick (with MacOS) with Terminal

```
diskutil list
diskutil unmountDisk /dev/disk"Number?"
sudo dd bs=4m if=/Users/###/Downloads/ubuntu-12.04.5-desktop-i386.iso  of=/dev/rdisk"Number?" conv=sync
```
