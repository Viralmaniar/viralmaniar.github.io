---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Socks Tunnel"
date:   2019-07-07 16:15:00 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
  - Active Directory Hacking
tags:
  - SOCKS 
  - SOCKS Tunnel
  - SOCKS Proxy
---
- SOCKS 5 proxy tunnel:

  - ssh -D 1337 -f -C -q -N user@victimip.com
    - D: Tells SSH that we want a SOCKS tunnel on the specified port number (only ports between 1025-65536 are supported)
    - f: Forks the process to the background
    - C: Compresses the data before sending it
    - q: Uses quiet mode
    - N: Tells SSH that no command will be sent once the tunnel is up
    
   - Verify that the tunnel is up and running with this command:
    - ps aux | grep ssh
    
   - Configuring Firefox to Use the Tunnel:
    - set the SOCKS host as 'localhost' on the attacker machine
    - set the port numer to 1337
   
   - Browse the internal application from the victim's network on an attacker machine through Firefox
  
