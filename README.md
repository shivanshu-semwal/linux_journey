# Linux Journey

## Index

*   [Commands](./commands.md)
*   [Package Management](./package_management.md)
*   [VIM](./vim.md)
*   [Conda Environment Management](./conda.md)
*   [Terminal Tricks](./play_with_terminal.md)
*   [Customizations](./some_customizations.md)

## How it all started

When I entered programming world and started watching videos about programming, I saw many programmers use Linux rather than Windows. So I started a reserach on Linux OS.

## What is Linux

Linux is an open-source operating system whose kernel was developed by infamous Linus Torvalds. That project was forked by many others and so many new distros arrived in the OS market. What was nice about them was that each of them was focused towards a particular job. Since these OS's are open-source they are less prone to security flaws as whenever a bug is found it is fixed.

There are two types of these distro on the basis of how they are updated:
*   Rolling release - you only have to __install it once__ and it gets updated on its own to its new vesions.
*   Point release - you have to upgrade to new versions and sometimes this may remove some old apps.

## Which distro I used and why?

I started with Ubuntu beacause it is friendly for new users and it has a huge community.

## How I began?

I first installed the Ubuntu on VMware Player(free version). You can use other softwares like OracleVirtualBox.
After using it for one year I dual booted my laptop using Ubuntu.

## How I dual booted.

I have Lenovo Legion Y540 having NVIDIA GeForce GTX 1650 Mobile. 

>Lenovo is one of the best and top manufactures that support and sells Linux customized laptops.

Steps I did to dual boot are:-

*   I have a 230GB ssd and 1TB hdd. I shrunk the 230GB ssd by 100gb to install ubuntu.
*   Made a usb bootable stick for ubuntu 20.04 LTS.
*   Disabled secure boot from BIOS.
*   Booted using the usb stick and choose custom partition.
*   Here is how I did partitions:
    * __Size__: 512 MB      __filesystem__: fat32       __mount point__: /boot/efi      __flags__: boot
    * __Size__: 4099 MB     __filesystem__: linuxswap   
    * __Size__: remaining free space    __filesystem__: ext4    __mount point__: /root

>You should especially make a different efi partition for ubuntu as I did (to avoid the problems during updates when window overwrites the efi partiton)

## What where the problems I faced after installing ubuntu?

### Brightness not working and unable to suspend the laptop

I was unable to change the brightness of the screen and recover back from suspend.

*__How I fixed this::__*

Install Nvidia driver:

```bash
# addding a paa
sudo add-apt-repository ppa:graphics-drivers/ppa

# installing nvidia driver
sudo apt install nvidia-driver-440

# installing the other driver if the above one not works
sudo apt install dkms nvidia-driver-440
```

Now edit the configuration file for the nvidia driver::

__First open the congfig file with a text editor with root previliges and modify its contents as follows::__

``` bash

# open config file in text editor (i used nano)
sudo nano /usr/share/X11/xorg.conf.d/10-nvidia.conf

# modify the contents with following
Section "Device"
    Identifier     "Device0"
    Driver         "nvidia"
    VendorName     "NVIDIA Corporation"
    BoardName      "Quadro K1000M"
    Option         "RegistryDwords" "EnableBrightnessControl=1"
EndSection

#reboot the laptop
reboot
```
This fixed my brightness control and suspend problem.

### Unable to write on my 1TB HDD

This problem occurs because windowds don't shut down completely and stores some hyberfile on the disk.
When Ubuntu sees some problem with the disk it makes it read-only.

To fix this you either have to disable the fast startup option or shut-down the windows completely by holding the left-shift key while shutting down. I choose the second option. 

