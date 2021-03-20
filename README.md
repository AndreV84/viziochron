# viziochron
# Flashing NX device with hdmi display or emulator conencted, headless mode
1. It is required to either form the Linux_for_Tegra folder created at Host_PC with sdkmanager or with downloading rootfs from Downloads portal.


Then the file l4t_create_default_user.sh needs to be copied to the Linux_for_Tegra Folder to be run from there like:
```
sudo ./l4t_create_default_user.sh -u nvidia -p nvidia -a
```

Then flashing takes place given the device is in the recovery mode
```
sudo ./flash.sh -S 64GiB xavier-nx-devkit mmcblk0p1
```
