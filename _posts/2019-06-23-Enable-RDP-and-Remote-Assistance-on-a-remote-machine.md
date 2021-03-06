---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Enable RDP and Remote Assistance on A Remote Machine"
date:   2019-06-23 13:49:40 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - RDP
  - Remote Desktop
  - Registry Key Hacking
  - Windows Security
  - Active Directory Hacking
---
<pre>
reg add "hklm\system\currentControlSet\Control\Terminal Server" /v "AllowTSConnections" /t REG_DWORD /d 0x1 /f
reg add "hklm\system\currentControlSet\Control\Terminal Server" /v "fDenyTSConnections" /t REG_DWORD /d 0x0 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fAllowToGetHelp /t REG_DWORD /d 1 /f
netsh advfirewall set rule group="remote administration" new enable="yes"
netsh advfirewall firewall set rule group="remote administration" new enable=yes
netsh advfirewall firewall set rule group="remote desktop" new enable=Yes
netsh advfirewall firewall set rule group="remote desktop" new enable=Yes profile=domain
netsh advfirewall firewall set rule group="remote desktop" new enable=Yes profile=private
netsh firewall add portopening TCP 3389 "Remote Desktop"
netsh firewall set service RemoteDesktop enable
netsh firewall set service RemoteDesktop enable profile=ALL
netsh firewall set service RemoteAdmin enable
sc config TermService start= auto
net start Termservice
</pre>

<pre>
- psexec \\hostname reg add "hklm\system\currentcontrolset\control\terminal server" /f /v fDenyTSConnections /t REG_DWORD /d 0
- psexec \\hostname netsh firewall set service remoteadmin enable
</pre>
