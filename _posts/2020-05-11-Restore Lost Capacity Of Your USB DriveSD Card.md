---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Restore Lost Capacity Of Your USB Drives and SD Cards"
date:   2020-05-11 22:57:00 +1000
categories:
  - USB Forensics
  - Forensics
  - USB Drops
tags:
  - USB
  - Recovery 
  - Forensics
---

I was playing with the Pi hole on one of my old Raspberry Pi and noticed that my 32 GB SanDisk Micro SD card was showing only 100 MB as space. I tried multiple method to recover the card space but was unable to get it back. 

Following method worked to get the space to it's orginal:

1. Open run(Win+R) and type 'diskpart', Enter
2. Type 'list disk', Enter
3. Type 'select disk #', Enter (to select a disk, where # is the number of the disk Windows screw-balled. Usually, the device is disk 1, but it's always best to make sure.)
4. Type 'select partition 1', Enter
5. Type 'delete partition', Enter
6. Type 'partition', Enter
7. Type 'clean', Enter:
8. Type 'create partition primary', Enter
9. Type 'format', Enter, this will format your drive
