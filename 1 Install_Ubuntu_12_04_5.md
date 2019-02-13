# Install Ubuntu 12.04.5

[Download Ubuntu 32bit](http://releases.ubuntu.com/precise/)

## create USB Stick (with MacOS) with Terminal

```
internet:~ user$ diskutil list
/dev/disk0 (internal, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
[..]

/dev/disk1 (internal, virtual):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
[..]

/dev/disk2 (disk image):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
[..]

/dev/disk3 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     Apple_partition_scheme                        *16.1 GB    disk3
   1:        Apple_partition_map                         4.1 KB     disk3s1
   2:                  Apple_HFS                         2.4 MB     disk3s2

internet:~ user$ diskutil unmountDisk /dev/disk3
Unmount of all volumes on disk3 was successful
internet:~ user$ sudo dd bs=4m if=/Users/user/Downloads/ubuntu-12.04.5-desktop-i386.iso  of=/dev/rdisk3 conv=sync
Password: "typeIt"
189+0 records in
189+0 records out
792723456 bytes transferred in 43.121733 secs (18383386 bytes/sec)
internet:~ user$
```

## No Update to 14.04 LTS
