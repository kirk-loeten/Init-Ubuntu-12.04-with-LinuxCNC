# Install Realtime Kernel

[Kernel install discrition on linuxcnc.org](http://linuxcnc.org/docs/2.7/html/getting-started/getting-linuxcnc.html#_installing_linuxcnc)

Run the following to bring the machine up to date with the latest packages in Ubuntu Precise.
```
sudo apt-get update
sudo apt-get dist-upgrade
```
Add the LinuxCNC Archive Signing Key to your apt keyring by running
```
sudo apt-key adv --keyserver hkp://keys.gnupg.net --recv-key 3cb9fd148f374fef
```
Add a new apt source
```
sudo add-apt-repository "deb http://linuxcnc.org/ precise base 2.7-rtai"
```
Fetch the package list from linuxcnc.org.
```
sudo apt-get update
```
Install the RTAI kernel and modules by running
```
sudo apt-get install linux-image-3.4-9-rtai-686-pae rtai-modules-3.4-9-rtai-686-pae
```
If you want to be able to build LinuxCNC from source using the git repo, also run
```
sudo apt-get install linux-headers-3.4-9-rtai-686-pae
```
Reboot, and make sure you boot into the rtai kernel. When you log in, verify that the kernel name is 3.4-9-rtai-686-pae.
```
uname -r
```
