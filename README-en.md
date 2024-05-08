## Table of Contents

* [The Build](#the-build)
  * [BIOS Settings](#bios-settings)
* [Partition Boot Drive](#partition-boot-drive)
* [Prepare Install Media](#prepare-install-media)
* [Install the Bootloader](#install-the-bootloader)
* [Kernel Extensions](#kernel-extensions)
  * [Mandatory](#mandatory)
  * [Post Installation](#post-installation)
  * [Optional](#optional)
* [Video Demonstrations](#video-demonstrations)
* [Compatibility](#compatibility)
* [Releases](#releases)
* [License](#license)
* [Warranty](#warranty)
* [Download](#download)

## The Build
View the complete [specs](https://www.dualbootpc.com/systems/laptop/) at `http://sipyl.us/2Jslljx`

## Prepare Install Media
1. Download the installer for [macOS Sierra](https://www.dualbootpc.com/software/system/macos/sierra/) from the Mac App Store.
2. Open Terminal and format the target 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) with the following command:

    `diskutil partitionDisk /dev/{DISK_ID} GPT JHFS+ "SierraUSB" 100%` 
    
3. Partition the 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) and give 12 GB to the **SierraUSB** and 4 GB to **Post Installation**.
4. [Create the bootable macOS installer](https://www.dualbootpc.com/guide/creating-a-usb-installer/): Instructions works for [OS X Mavericks](https://www.dualbootpc.com/software/system/macos/mavericks/) through [macOS Monterey](https://www.dualbootpc.com/software/system/macos/monterey/).

    `sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/SierraUSB --applicationpath /Applications/Install\ macOS\ Sierra.app`
5. Once the program finishes in the Terminal, your [USB drive](https://www.dualbootpc.com/hardware/usb/) will be called the following:

    `Install macOS Sierra`
    
## Install the Bootloader
**USB Flash Drive**
* Download the [Clover](https://www.dualbootpc.com/software/bootloader/clover/) 2.4k r4934 installer.
* Install Clover 2.4k r4934 to your 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) device and customize with the following options:
  * Clover for UEFI booting only
  * Install Clover in the ESP
  * UEFI Drivers
    * Mandatory drivers
      * ApfsDriverLoader-64.efi
      * AptioMemoryFix-64.efi
      * HFSPlus.efi
    * Recommended drivers
      * AudioDxe-64.efi (Enables Boot Sound in compatible themes)
      * NvmExpress-64.efi (Enabled The Detection of the NVMe drive)

**Boot Drive**
* Export the **BOOT** and the **CLOVER** from the EFI Folder on the USB Flash Drive and import to the EFI Folder on the boot drive.
* Install [Clover](https://www.dualbootpc.com/software/bootloader/clover/) 2.5k r5119 to your boot drive and customize with the **additional** options:
  * Install RC Scripts in the target volume
  * Install Clover Preference Pane (Select during Post Installation)
* Eject all USB Flash Drives and restart to the BIOS.
* Set the boot drive with Clover as the Primary and exit.
