---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Living Off The Land Binaries - AT Command"
date:   2019-11-15 17:48:00 +1000
categories:
  - LOTL
  - EDR
  - Internal Pentest
tags:
  - LOTL
  - EDR
  - Living Off The Land
---

Examples of  at.exe being used maliciously in order to establish persistence in a manner almost identical to schtasks use as a lolbin (enter hashes into virustotal search and view behavioural analysis report in order to verify):

a5b310c1fe984d5e1e85342223d7ed02

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\blastclnnn.exe
a5b310c1fe984d5e1e85342223d7ed02

at
c:\windows\system32\cmd.exe /c at /delete /yes
a5b310c1fe984d5e1e85342223d7ed02

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\blastclnnn.exe
a5b310c1fe984d5e1e85342223d7ed02

a5b310c1fe984d5e1e85342223d7ed02

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\blastclnnn.exe
a5b310c1fe984d5e1e85342223d7ed02

at
c:\windows\system32\at.exe at /delete /yes


at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\svchost .exe
24b6e8beeabb93d2162656ef78eb249b

at
c:\windows\system32\at.exe at /delete /yes
--
83b2aaea4f34a34c4692119eba6a068f

at
c:\windows\system32\cmd.exe /c at /delete /yes
83b2aaea4f34a34c4692119eba6a068f

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\ssvichosst.exe
83b2aaea4f34a34c4692119eba6a068f



ae573135138ab4b04fa5c46ba756833a

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\khatra.exe
--
ae573135138ab4b04fa5c46ba756833a

at
c:\windows\system32\cmd.exe /c at /delete /yes
ae573135138ab4b04fa5c46ba756833a

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\khatra.exe
ae573135138ab4b04fa5c46ba756833a

at
c:\windows\system32\cmd.exe /c netsh firewall add allowedprogram program=c:\windows\system32\khatra.exe name=system
ae573135138ab4b04fa5c46ba756833a

at
c:\windows\system32\at.exe at /delete /yes
--
ae573135138ab4b04fa5c46ba756833a

at
c:\windows\system32\cmd.exe /c at /delete /yes
ae573135138ab4b04fa5c46ba756833a

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\khatra.exe
ae573135138ab4b04fa5c46ba756833a





at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\gphone.exe
4c7a945724c793921f98d79521b906ab

at
c:\windows\system32\cmd.exe /c cacls \system volume information /e /g <user>:f
4c7a945724c793921f98d79521b906ab

at
c:\windows\system32\at.exe at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\gphone.exe
4c7a945724c793921f98d79521b906ab

at
c:\windows\system32\at.exe at /delete /yes
--
57af5363ba26325232268e7bd72f8e15

at
c:\windows\system32\cmd.exe /c at /delete /yes
57af5363ba26325232268e7bd72f8e15

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\chrome.exe
--
57af5363ba26325232268e7bd72f8e15

at
c:\windows\system32\cmd.exe /c at /delete /yes
57af5363ba26325232268e7bd72f8e15

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\chrome.exe
--
57af5363ba26325232268e7bd72f8e15



0129cca7cc56c0356d62662311c6c09c

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\winhelp.exe
0129cca7cc56c0356d62662311c6c09c

at
c:\windows\system32\at.exe at /delete /yes


954a5a16e9a305a48c532fcf59ae6430

at
c:\windows\system32\at.exe at.exe 18:30  /every:monday,tuesday,wednesday,thursday,friday,saturday,sunday  \program files\winrar\language\s.cmd 
954a5a16e9a305a48c532fcf59ae6430

at
c:\windows\system32\at.exe at.exe 18:00  /every:monday,tuesday,wednesday,thursday,friday,saturday,sunday  \program files\winrar\language\s.cmd 
954a5a16e9a305a48c532fcf59ae6430

at
c:\windows\system32\at.exe at.exe 19:30  /every:monday,tuesday,wednesday,thursday,friday,saturday,sunday  \program files\winrar\language\s.cmd 
954a5a16e9a305a48c532fcf59ae6430



f3015578915b43611267ff638ede87fc

at
c:\windows\system32\at.exe at 23:17:00 /every:t,m,th,f,w,s,su cmd.exe /c attrib -h c:\windows\system32\drivers\etc\hosts && copy \docume~1\<user>~1\locals~1\temp\324025 c:\windows\system32\drivers\etc\hosts /y && attrib +h c:\windows\system32\drivers\etc\hosts && erase \docume~1\<user>~1\locals~1\temp\b14eb41856153549d686c236f0411ab2c2ecbecd36db5de4179ad4e3019f7491 
--
03cdafef43bb4aa91b40939b8c102631

at
c:\windows\system32\cmd.exe /c at /delete /yes
03cdafef43bb4aa91b40939b8c102631

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\blastclnnn.exe
03cdafef43bb4aa91b40939b8c102631

at
c:\windows\system32\cmd.exe /c at /delete /yes
03cdafef43bb4aa91b40939b8c102631

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\blastclnnn.exe
03cdafef43bb4aa91b40939b8c102631


c13e5af0535a008dd81608cc0d1db563

at
c:\windows\system32\at.exe at 19:00 /interactive /every:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,
24,25,26,27,28,29,30,31 c:\windows\system32\calck.exe
c13e5af0535a008dd81608cc0d1db563

at
c:\windows\system32\at.exe at 20:00 /interactive /every:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,
24,25,26,27,28,29,30,31 c:\windows\system32\calck.exe
c13e5af0535a008dd81608cc0d1db563

at
c:\windows\system32\at.exe at 21:00 /interactive /every:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,
24,25,26,27,28,29,30,31 c:\windows\system32\calck.exe
c13e5af0535a008dd81608cc0d1db563

at
c:\windows\system32\at.exe at 22:00 /interactive /every:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,
24,25,26,27,28,29,30,31 c:\windows\system32\calck.exe
c13e5af0535a008dd81608cc0d1db563

at
c:\windows\system32\at.exe at 23:00 /interactive /every:1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,
24,25,26,27,28,29,30,31 c:\windows\system32\calck.exe



7f2bdb593f9c1504c4931272b4721ed2

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\scvhost.exe
7f2bdb593f9c1504c4931272b4721ed2

at
c:\windows\system32\at.exe at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\scvhost.exe
7f2bdb593f9c1504c4931272b4721ed2

at
c:\windows\system32\at.exe at /delete /yes
7f2bdb593f9c1504c4931272b4721ed2

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\scvhost.exe
7f2bdb593f9c1504c4931272b4721ed2

at
c:\windows\system32\at.exe at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\scvhost.exe
--


2a721ab3a874361f9ba20b1edca8a4a0

at
c:\windows\system32\cmd.exe /c at /delete /yes
2a721ab3a874361f9ba20b1edca8a4a0

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\system3_.exe
--



18d6ca8e755531e61fe1991799661c20

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\word.exe
18d6ca8e755531e61fe1991799661c20

at
c:\windows\system32\cmd.exe /c at /delete /yes
18d6ca8e755531e61fe1991799661c20




at
c:\windows\system32\cmd.exe /c at /delete /yes
794066195d14aef9e38f070306564dc0

at
c:\windows\system32\cmd.exe /c at 09:00 /interactive /every:m,t,w,th,f,s,su c:\windows\system32\system3_.exe
794066195d14aef9e38f070306564dc0

1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:15 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:20 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:25 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:30 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:35 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:40 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:45 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:50 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 01:55 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 02:00 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 02:05 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 02:10 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041

at
c:\windows\system32\at.exe at 02:15 /every:m,t,w,th,f,s,su \down2\<machine_name>0800278be8aa.exe
1df9f8a0728b078d1047cb908628d041


at
c:\windows\system32\at.exe at 23:00  /interactive c:\windows\58a73044\svchsot.exe
bf7758800ea155f666a59d169d6719ed


at
c:\windows\system32\at.exe at.exe 9:30  /every:monday,tuesday,wednesday,thursday,friday,saturday,sunday  \program files\winrar\language\s.cmd 
79118ed095c4d6901b4712666996bbc3

at
c:\windows\system32\at.exe at.exe 9:00  /every:monday,tuesday,wednesday,thursday,friday,saturday,sunday  \program files\winrar\language\s.cmd 
79118ed095c4d6901b4712666996bbc3

at
c:\windows\system32\at.exe at.exe 10:30  /every:monday,tuesday,wednesday,thursday,friday,saturday,sunday  \program files\winrar\language\s.cmd 
79118ed095c4d6901b4712666996bbc3


698928995ff4708061d2d2c2579b2ebc

at
c:\windows\system32\at.exe at 9:00  /interactive c:\windows\0f658469\svchsot.exe
698928995ff4708061d2d2c2579b2ebc



698928995ff4708061d2d2c2579b2ebc

at
c:\windows\system32\at.exe at 19:00  /interactive c:\windows\0f658469\svchsot.exe
698928995ff4708061d2d2c2579b2ebc

at
c:\windows\system32\at.exe at 20:00  /interactive c:\windows\0f658469\svchsot.exe
698928995ff4708061d2d2c2579b2ebc

at
c:\windows\system32\at.exe at 21:00  /interactive c:\windows\0f658469\svchsot.exe
698928995ff4708061d2d2c2579b2ebc

at
c:\windows\system32\at.exe at 22:00  /interactive c:\windows\0f658469\svchsot.exe
698928995ff4708061d2d2c2579b2ebc

at
c:\windows\system32\at.exe at 23:00  /interactive c:\windows\0f658469\svchsot.exe
698928995ff4708061d2d2c2579b2ebc

Thanks to https://freddiebarrsmith.com/at.txt
