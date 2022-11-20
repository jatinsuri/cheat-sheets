# Install latest MacOS on unsupported hardware
Installing MacOS Ventura on MacBook Pro Retina Late 2013 (MacBookPro11,1) is now possible thanks to the Opencore legacy patcher.

`Partitioning Note`
Disk partitioning in MacOS installers is not very flexible. It is a good idea to partition the disk manually by booting a linux live USB and setup partitions. 

## OpenCore Legacy Patcher (OCLP)
- [Github: dortania/Opencore-Legacy-Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher)
- [Documentation](https://dortania.github.io/OpenCore-Legacy-Patcher/START.html#how-do-i-get-started)
- [OpenCore Legacy Patcher App](https://github.com/dortania/OpenCore-Legacy-Patcher/releases)

Follow the steps in the docs linked above and they are pretty straightforewards. Here are some key take aways:
- Download and install OCLP app
- Create macOS Installer
  - Download macOS Installer
  - Flash Installer to USB
- Build and Install OpenCore to USB
- Reboot and hold Option key
  - Select EFI Boot
  - Select Install MacOS `version name`
  - Takes a while and several reboots
  - Keep the USB connected
  
  Post installation
  - Download and install OCLP app
  - Change settings (for example disable Show Boot Picker)
  - Build and Install OpenCore to internal drive
  - Unplug USB and reboot
  - Select EFI (if Boot Picker wasn't disabled)