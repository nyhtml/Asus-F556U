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
View the complete [specs](https://www.dualbootpc.com/systems/desktop/arctic-fox/specs/) at `http://gixxer.us/2Jslljx`

## Prepare Install Media
1. Download the installer for [macOS Sierra](https://www.dualbootpc.com/software/system/macos/sierra/) from the Mac App Store.
2. Open Terminal and format the target 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) with the following command:

    `diskutil partitionDisk /dev/{DISK_ID} GPT JHFS+ "SierraUSB" 100%` 
    
3. Partition the 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) and give 12 GB to the **SierraUSB** and 4 GB to **Post Installation**.
4. [Create the bootable macOS installer](https://www.dualbootpc.com/guide/creating-a-usb-installer/): Instructions works for [OS X Mavericks](https://www.dualbootpc.com/software/system/macos/mavericks/) through [macOS Monterey](https://www.dualbootpc.com/software/system/macos/monterey/).

    `sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/SierraUSB --applicationpath /Applications/Install\ macOS\ Sierra.app`
5. Once the program finishes in the Terminal, your [USB drive](https://www.dualbootpc.com/hardware/usb/) will be called the following:

    `Install macOS Sierra`
    
