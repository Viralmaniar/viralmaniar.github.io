---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Extracting NTDS.DIT File"
date:   2019-06-22 15:29:10 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - Registry Key Hacking
  - Windows Security
  - Active Directory Hacking
---
- Clear text proxy credentials of putty:
  - reg query "HKCU\Software\SimonTatham\PuTTY\Sessions"
  - This lists out all available sessions with putty.
  - Use individual session names to see the 'proxy password' field value.
  
  
