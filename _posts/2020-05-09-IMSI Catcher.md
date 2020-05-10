---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "IMSI Catcher"
date:   2020-05-09 07:34:24 +1000
categories:
  - SDR
  - Radio Frequency
tags:
  - 2G -GSM Hacking
  - 4G - LTE Hacking
  
---
Thanks to Keld Norman

Here is the guide to create the IMSI catcher with a cheap SDR dongle:

 1. Install Ubuntu 16.04.2 LTS
 Go to http://releases.ubuntu.com/16.04/  and download the Ubuntu 16.04 LTS version of a 64bit desktop.

 Here is the direct link that worked when i wrote this guide:
 http://releases.ubuntu.com/16.04/ubun...
 
 If you use a VM then give it a min. of 2Gb Memory. Compiling might crash if there is not enough memory
 I gave my VM 1 cpu, 2G memory, 20Gb disk, removed the printer and sound card and left the USB in usb2.0 mode.
  
 Update ubuntu after the installation is done:
 sudo apt-get update && sudo apt-get upgrade -y
 reboot
 
 2. Install GNU Radio GSM modules / gr-gsm
 sudo apt-get install git python-pip 
 sudo pip install PyBOMBS
 sudo pybombs prefix init /usr/local -a default_prx
 sudo pybombs config default_prefix default_prx
 sudo pybombs recipes add gr-recipes git+https://github.com/gnuradio/gr-recipe...
 sudo pybombs recipes add gr-etcetera git+https://github.com/gnuradio/gr-etcete...
 sudo pybombs install gr-gsm # This one could take hours to complete
 sudo ldconfig

 - Plug in the SDR-Dongle and check it is detected with dmesg. Then test if gr-gsm works: 
 sudo grgsm_livemon # You should see the blue signal fluctuate

 - If you see this error - you forgot sudo in front of grgsm_livemon 
 - Using device #0 Generic RTL2832U OEM
 - usb_open error -3
 - Please fix the device permissions, e.g. by installing the udev rules file rtl-sdr.rules
 - FATAL: Failed to open rtlsdr device.

 3. Get the python script to grap the data and present them nicely:
 - Install the pre reqs.
 sudo apt install python-numpy python-scipy python-scapy 
 
 - Get the scripts
 git clone https://github.com/Oros42/IMSI-catche...
 
 - Update the network providers list
 python IMSI-catcher/mcc-mnc/update_codes.py  
 
 # In terminal 1
 cd IMSI-catcher
 sudo python simple_IMSI-catcher.py

 # In terminal 2
 Start the radio wave sniffer on a channel where a GSM base station/tower transmits in your area.
 #-----------------
 airprobe_rtlsdr.py -f 943400000 # this is the same program called grgsm_livemon
 
 Now, change the frequency and stop it when you have output like in the console behind the gui:<BR>
 <I>
 4c 69 6b 65 56 69 64 65 6f 3d 53 65 6e 64 63 68 6f 63 6f 6c 61 74 65 <BR>
 00 6b 65 6c 64 2e 6e 6f 72 6d 61 6e 40 67 6d 61 69 6c 2e 63 6f 6d 00
 </I>
 Watch terminal 1 and wait. The TMSI/IMSI numbers should appear shortly
 
 If nothing appears after 1 min, change the frequency.

 You can also watch the GSM packets in wireshark like this:
 sudo apt-get install -y wireshark tshark # NB: tshark is a commandline version of wireshark
 sudo wireshark -k -Y '!icmp && gsmtap' -i lo # ignore errors about not running wireshark as root..
