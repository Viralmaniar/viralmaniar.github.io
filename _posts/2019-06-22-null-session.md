---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Null Session"
date:   2019-06-22 15:29:10 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - Null Session
  - Active Directory Hacking
---

- Active Reconnaissance Methods:
  - Null Session:
    - net use \\[DA IP Address]\ipc$ "" "/user:"
    - here we're trying to connect using a blank password and username
    - if you see "the command completed successfully". At this moment we'be made successful connection.
  
  - Confirm Null Session is mapped:
    - net use
    - Now one should see a mapping to the IPC$ share to each computer to which attacker machine is connected
      <pre>
      C:\WINDOWS\system32>net use
      New connections will be remembered.
      
      Status    Local   Remote              Network
      ______________________________________________________
      OK                \\IP\$IPC           Microsoft Windows Network
      </pre>
      
- Once an attacker creates an successful null connection, you can use tools like Dumpsec or Winfo to gether informaiton about user and password policy. 

- Download winfo: http://www.ntsecurity.nu/toolbox/winfo
- Download Dumpsec: http://www.systemtools.com/somarsoft/index.html

 
