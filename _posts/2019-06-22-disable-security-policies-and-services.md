---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Disable Security Policies and Services"
date:   2019-06-22 15:29:10 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - Windows Services
  - Windows Security
  - Security Policies
  - Active Directory Hacking
---

- Disable security policies and services to avoid detection by Blue team
  - Auditpol /set /Category:System /failure:disable
- Services.msc:
  - As an attacker disable these services to clear your trace
  - Blue team checks these logs to find stuff
  - <b>Windows Event Collector</b>: This service manages persistent subscriptions to events from remote sources that support WS-Management protocol. This includes Windows Vista event logs, hardware and IPMI-enabled event sources. The service stores forwarded events in a local Event Log. If this service is stopped or disabled event subscriptions cannot be created and forwarded events cannot be accepted.
    - C:\WINDOWS\system32>sc stop Wecsvc
  - <b>Windows Event Log</b>: This service manages events and event logs. It supports logging events, querying events, subscribing to events, archiving event logs, and managing event metadata. It can display events in both XML and plain text format. Stopping this service may compromise security and reliability of the system.
    - C:\WINDOWS\system32>sc stop EventLog
  
  
