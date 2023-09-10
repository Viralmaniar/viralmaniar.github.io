---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  " Installing Kali in AWS EC2 Instance"
date:   2023-09-10 00:18:25 +1000
categories:
  - Offnesive Security
  - Security
  - Kali
tags:
  - Offensive Security
  - Kali
---

- sudo passwd kali
- sudo apt-get update
- sudo apt-get install xrdp lxde-core lxde tigervnc-standalone-server -y
- cd /
- sudo sed -i 's/allowed_users=.*/allowed_users=kali/' /etc/X11/Xwrapper.config
- sudo service xrdp start
- sudo systemctl enable xrdp

The below commands are optional to install the latest OS updates
- sudo apt-get update 
- sudo apt-get upgrade
