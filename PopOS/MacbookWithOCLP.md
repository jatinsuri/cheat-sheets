# Dual boot Linux on Macbook running OpenCore Legacy Patcher (OCLP)
OCLP allows older unsupported macbooks to run the latest MacOS versions. OCLP takes over the boot process by installing itself to the EFI System Partition (ESP).

[OpenCore Multiboot](https://dortania.github.io/OpenCore-Multiboot/) has extensive documentation about multi boot support offered by OpenCore and it has support for both Windows and Lunux.

## Dualbooting with Linux the OCLP way
[Dualbooting with Linux](https://dortania.github.io/OpenCore-Multiboot/oc/linux.html#method-a-openlinuxboot) describes all the methods that can be used. Method A is the simplest.

## Dualbooting with Linux without OCLP
This method relies on creating an extra ESP on the internal disk which can then be used as the /boot partition during a Linux installation.

### Pop! OS install
- Create bootable USB medium with Pop OS install or simply copy the downloaded image to a Ventoy USB (if there is one at hand).
- Reboot + Option Key, select EFI boot with the external disk icon or if using Ventoy, then select EFI boot internal (OCLP), keep Option pressed and then select VENTOYEFI, then choose grub2 boot.
- Within the installer, select custom setup and create partitions for /boot/efi and / filesystems.
- Reboot when install is done, then select EFI boot with the HDD icon.
