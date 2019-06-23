---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Skeleton Key Attack"
date:   2019-06-23 13:44:10 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - Windows Security
  - Skeleton Key Attack
  - Active Directory Hacking
---

- Skeleton Key Attack: This attack is very tricky. It makes the secondary password for the same user. Many malware takes advantage of this attack to create persistence in a network. Both passwords works for the Domain Users. 

- Things Needed:
  - Domain Admin rights
  - Mimikatz
  - Control of every domain controller in a network

- Mimikatz Commands:
  - privilege::debug 
  - misc::skeleton
