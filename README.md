# The IdeaPad ACPI Extras kernel modules for ThinkBook 2024 NoteBooks

This kernel module solves two problems:

1. Dead Sleep: The laptop turning off after closing the lid.
2. Fn+F5/6 shutdown: The laptop turning off after pressing Fn+F5 or Fn+F6(not frequently).

Tested and works on:

- ThinkBook 2024 16+ IMH with Ubuntu 24.04 with kernel 6.9.3-060903-generic
- ThinkBook 2024 14 G6+ AHP with Arch Linux with kernel 6.10.9-x64v2-xanmod1-1

## Usage

### Install via dkms for Ubuntu

```shell
make
sudo make install-dkms
sudo cp dkms/blacklist-ideapad-laptop-tb-dkms.conf /etc/modprobe.d/
sudo reboot

# Uninstall
sudo make uninstall-dkms
sudo rm /etc/modprobe.d/blacklist-ideapad-laptop-tb-dkms.conf
sudo reboot
```

### Install via makepkg for Arch Linux

```shell
cd aur
makepkg -si
sudo reboot

# Uninstall
yay -R ideapad-laptop-tb-dkms
```

## Known bugs

- The Fn + F4(Mute Mic func) will not work.