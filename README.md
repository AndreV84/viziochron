
# Flashing of NX device with hdmi display or emulator connected in headless mode
First, Linux_for_Tegra folder has to be created at Host_PC either with sdkmanager or with downloading rootfs archive from Downloads portal.


Second, the file l4t_create_default_user.sh needs to be copied to the Linux_for_Tegra Folder to be run from there:
```
sudo ./l4t_create_default_user.sh -u nvidia -p nvidia -a
```
Before flashing the device needs to be put into the recovery either via a software trigger listed below or  by shortcutting pins 9-10 by the time the device gets powered ON with further release of the shortcut.
```
sudo reboot --force forced-recovery
```
For Jetson Xavier NX Developer Kit:


1)Ensure that your Jetson Xavier NX developer kit is powered off, and that a 16 GB or larger size microSD card is inserted in the SD card slot

2)To ensure that the developer kit starts in Force Recovery Mode, place a jumper across pins 9 and 10 (FC REC and GND) of the button header (J14), located on the edge of the carrier board under the Jetson module.

3)Connect the included power adapter to J16. The developer kit powers on and enters Force Recovery mode.

4)Remove the jumper from pins 9 and 10 of the button header.


<img src="https://developer.ridgerun.com/wiki/images/4/4a/Jetson-xavier-nx-back-view.png" alt="Image from Ridregun website" >

5)Continue the software installation.

Then flashing takes place given the device is in the recovery mode. Also the  mini usb-B of the Jetson NX needs to be connected to Host PC USB-A. 

source https://docs.nvidia.com/jetson/l4t/index.html#page/Tegra%20Linux%20Driver%20Package%20Development%20Guide/quick_start.html
```
sudo ./flash.sh -S 56GiB xavier-nx-devkit mmcblk0p1
```

# Flashing AGX [32GB eMMC version ]
AGX could be put into recovery mode via hardware method : pressing the middle force recovery button while powering ON or resetting the device or the software trigger could be used

<img src="http://linuxgizmos.com/files/nvidia_xavier_devkit5.jpg" alt="image from linuxgizmo middle recovery button" >

```
sudo reboot --force forced-recovery
```

the recovery USB cable needs to beconnected before reflashed. Only one of the two USB-C ports could be used for reflashing as depicted below
<img src="https://developer.ridgerun.com/wiki/images/thumb/1/16/FrontDeveloperKit.png/600px-FrontDeveloperKit.png" alt="from ridgerun - flashing port">

```
sudo ./flash.sh -S 24GiB jetson-xavier mmcblk0p1 
```
