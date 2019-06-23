---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Extracting Juicy Information from Registry"
date:   2019-06-23 13:48:10 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - Registry Key Hacking
  - Windows Security
  - Active Directory Hacking
---
- reg query "HKCU\Software\ORL\WinVNC3\Password"
- reg query HKEY_LOCAL_MACHINE\SOFTWARE\RealVNC\WinVNC4 /v password
- reg query "HKCU\Software\SimonTatham\PuTTY\Sessions"
- reg query HKLM /f password /t REG_SZ /s 
- reg query HKCU /f password /t REG_SZ /s
- reg query "HKLM\SYSTEM\Current\ControlSet\Services\SNMP"
- reg query "HKLM\SOFTWARE\Microsoft\Windows NT\Currentversion\Winlogon"
- reg query "HKEY_LOCAL_MACHINE\ SOFTWARE\Microsoft\Windows\CurrentVersion\Group Policy\ History" /v DCName 
