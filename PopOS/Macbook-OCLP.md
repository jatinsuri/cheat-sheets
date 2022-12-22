# Dual boot Linux on Macbook running OpenCore Legacy Patcher (OCLP)
OCLP allows older unsupported macbooks to run the latest MacOS versions. OCLP takes over the boot process by installing itself to the EFI System Partition (ESP).

[OpenCore Multiboot](https://dortania.github.io/OpenCore-Multiboot/) has extensive documentation about multi boot support offered by OpenCore and it has support for both Windows and Lunux.

## Dualbooting with Linux the OCLP way
[Dualbooting with Linux](https://dortania.github.io/OpenCore-Multiboot/oc/linux.html#method-a-openlinuxboot) describes all the methods that can be used. Method A is the simplest.

## Dualbooting with Linux without OCLP
This method relies on creating an extra ESP on the internal disk which can then be used as the /boot partition during a Linux installation.

## Pop! OS install
- Create bootable USB medium with Pop OS install or simply copy the downloaded image to a Ventoy USB (if there is one at hand).
- Reboot + Option Key, select EFI boot with the external disk icon or if using Ventoy, then select EFI boot internal (OCLP), keep Option pressed and then select VENTOYEFI, then choose grub2 boot.
- Within the installer, select custom setup and create partitions for /boot/efi and / filesystems.
- Reboot when install is done, then select EFI boot with the HDD icon.

## Pop! OS wifi
Ensure that the following packages are installed:
- b43-fwcutter
- firmware-b43-installer
- bcmwl-kernel-source

## Considerations for Arch Linux
When installing Arch, make sure that the following extra packages are installed:
- linux-headers
- broadcom-wl-dkms
- networkmanager

Enabled NetworkManager in chroot before reboot:
```
systemctl enable NetworkManager.service
```

References:
- [Arch Linux on Macbook Pro Late 2013](https://sylvaindurand.org/installing-arch-linux-on-macbook-pro-late-2013/)
- [Installing Arch Linux on a MacBook Pro - Part 1](https://nickolaskraus.io/articles/installing-arch-linux-on-a-macbookpro-part-1/)
- [Installing Arch Linux on a MacBook Pro - Part 2](https://nickolaskraus.io/articles/installing-arch-linux-on-a-macbookpro-part-2/)
- [Installing Arch Linux on a MacBook Pro - Part 3](https://nickolaskraus.io/articles/installing-arch-linux-on-a-macbookpro-part-3/)
- [Arch Wiki: MacBookPro11,x](https://wiki.archlinux.org/title/MacBookPro11,x)
- [Install Arch Linux on Macbook Pro11,2 Retina](https://medium.com/@laurynas.karvelis_95228/install-arch-linux-on-macbook-pro-11-2-retina-install-guide-for-year-2017-2034ceed4cb2)
