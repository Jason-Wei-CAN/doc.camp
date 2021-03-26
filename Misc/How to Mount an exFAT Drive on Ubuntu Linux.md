# [How to Mount an exFAT Drive on Ubuntu Linux](#top)

exFAT (Extended File Allocation Table) is a proprietary Microsoft file system optimized for flash memory devices such as SD cards and USB flash drives. It was designed to replace the old 32bit FAT32 file system that cannot store files larger than 4 GB.

exFAT file system is supported by all the latest versions of Windows and macOS operating systems. Ubuntu, like most of the other major Linux distributions, doesn’t provide support for the proprietary exFAT filesystem by default.

If you are using Ubuntu as your operating system, chances are that at some point you will encounter an issue when trying to mount exFAT formatted USB drive.

When you plug in the USB drive your system will show a message like this:
```shell
    Error mounting /dev/sdb1 at /media/linuxize/USB: unknown file system ‘exfat’
```
![image](https://user-images.githubusercontent.com/1932458/112575796-66f0d680-8dc7-11eb-9568-44adb825b91d.png)
    
Unknown filesystem type exfat

In this tutorial, we’ll explain how to enable exFAT support on Ubuntu 18.04. The same instructions apply for Ubuntu 16.04 and any other Ubuntu-based distribution, including Kubuntu, Linux Mint and Elementary OS.

## How to Mount exFAT Drive on Ubuntu Linux

To be able to mount exFAT filesystem on Ubuntu you’ll need to install the free FUSE exFAT module and tools which provide a full-featured exFAT file system implementation for Unix-like systems.
Before installing the packages make sure the Universe repository is enabled on your system. Open your terminal either by using the Ctrl+Alt+T keyboard shortcut or by clicking on the terminal icon and type:

sudo add-apt-repository universe

Once the repository is enabled update the packages index and install the exfat-fuse and exfat-utils packages using the following commands:

```shell
sudo apt update 
sudo apt install exfat-fuse exfat-utils
```
That’s it! You can now open your file manager and click on the USB disk to mount it.
