---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Nmap Ping Sweep"
date:   2019-07-07 15:33:00 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
  - Active Directory Hacking
tags:
  - Nmap
  - Ping Sweep
---
- Ping sweep is the process of pinging an entire range of network ip addresses to find out which ones are online or alive. Nmap is an excellent tool to do this quickly and effectively.

- nmap -sP 192.168.1.1-255

- nmap -sP 192.168.1.1-255 -n
  - "-n" flag will disable dns resolution.
  
- nmap -sP 192.168.1.1-255 -n --max-rtt-timeout 50ms
  - Using lower roundtrip times, the accuracy may reduce, since some hosts may reply after the timeout and nmap won't be able to catch their replies.
