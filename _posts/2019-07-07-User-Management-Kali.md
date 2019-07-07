---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - User Management Kali"
date:   2019-07-07 16:08:00 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
  - Active Directory Hacking
tags:
  - User Management
  - Kali
---
- adduser user1
- passwd user1
  - type new password: xxxxxxxxxxxxxxx
  - type confirm password: xxxxxxxxxxxx
- Adding user to the sudoers hroup
  - usermod -a -G sudo user1
