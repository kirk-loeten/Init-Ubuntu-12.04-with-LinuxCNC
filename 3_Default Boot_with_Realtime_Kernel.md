# Default Boot with Realtime Kernel

Tip: https://askubuntu.com/questions/216398/set-older-kernel-as-default-grub-entry

## Look for kernelversion
```
$ grep -Ei 'submenu|menuentry ' /boot/grub/grub.cfg | sed -re "s/(.? )'([^']+)'.*/\1 \2/"

menuentry  Ubuntu, mit Linux 3.13.0-117-generic
menuentry  Ubuntu, with Linux 3.13.0-117-generic (recovery mode)
submenu "Previous Linux versions" {
menuentry  Ubuntu, mit Linux 3.13.0-32-generic
menuentry  Ubuntu, with Linux 3.13.0-32-generic (recovery mode)
menuentry  Ubuntu, mit Linux 3.4-9-rtai-686-pae
menuentry  Ubuntu, with Linux 3.4-9-rtai-686-pae (recovery mode)
menuentry "Memory test (memtest86+)" {
menuentry "Memory test (memtest86+, serial console 115200)" {
```
 "Previous Linux versions>Ubuntu, mit Linux 3.4-9-rtai-686-pae"

## Set Kernelversion as Default

```
$ sudo nano /etc/default/grub
```
Set **GRUB_DEFAULT** to **"Previous Linux versions>Ubuntu, mit Linux 3.4-9-rtai-686-pae"**

```
GRUB_DEFAULT="Previous Linux versions>Ubuntu, mit Linux 3.4-9-rtai-686-pae"
GRUB_HIDDEN_TIMEOUT=0
GRUB_HIDDEN_TIMEOUT_QUIET=true
GRUB_TIMEOUT=10
GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=""
```

**[CTRL] + O** save
**[CTRL] + X** exit

## Check Kernel

Reboot

```
$ uname -r
3.4-9-rtai-686-pae
```


Kernel is aktiv
