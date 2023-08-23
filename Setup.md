# Overview #
The following are general installations steps for dual booting Linux Mint Cinnamon on Macbook Pro model a1708.

# Flash Linux Iso #
Guide: https://linuxmint-installation-guide.readthedocs.io/en/latest/burn.html
Linux Mint Cinnamon Download: https://linuxmint.com/download.php

# Set Partitions #
Source: https://www.youtube.com/watch?v=KIgxEEzT9ek&t=575s (2:08)

In macos, open Disk Utility to create free space for linux:
1) Click Partition
2) Below disk image, click "+" button and then "Add Partition"
3) In "Partition Image"
   - Input a name
   - Format MS-DOS (FAT)
   - Input desired size for Linux
4) Hit "Apply"

# Installation #
Source: https://www.youtube.com/watch?v=KIgxEEzT9ek&t=575s (5:49)

Restart computer and and hold option to boot into bootable drive:
1) Select bootable drive
2) Follow installation steps until "Erase disk... " is show on window
   - Click "Something else... "
   - Select the new allocated partition and create free space by clicking "-" button
   - Allocate for EFI partition with "+" button:
     - Set 1 gb space
     - Format EFI
   - Allocate for root partition with "+" button:
     - Set remainder of space for system
     - Format Ext4
     - Mount point "/"
   - Set boot loader installation to partition that contains the EFI partition recently made
3) Hit install and finish rest of installation

# Fix Audio #
Source: https://forums.linuxmint.com/viewtopic.php?t=398113

Fresh out of the box the speakers and audio jack do not work, so open terminal:
1) Run the following
    - git clone git@github.com:egorenar/snd-hda-codec-cs8409.git
    - cd snd-hda-codec-cs8409
    - make
    - sudo make install
2) Reboot

# Issues #
1) The macbook's webcam is not identified by Linux; however there is a potential solution: https://forums.linuxmint.com/viewtopic.php?t=380393
2) Ocassionally the computer becomes incredibly hot when running even the lightest task. Some simple application take up gbs of memory.
3) Although audio can be heard, the speakers are not as good as the speakers under macos and often utter popping noises when changing volume.

