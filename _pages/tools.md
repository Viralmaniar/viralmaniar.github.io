---
permalink: /tools/
title: Tools
author_profile: true
layout: single
toc: true
toc_sticky: true
---

## Passhunt
Passhunt is a simple tool for searching of default credentials for network devices, web applications and more. Search through 523 vendors and their 2084 default passwords. 

![Passhunt](/assets/images/tools/Passhunt.PNG){: .align-center}

## Wifi-Dumper
This is an open source tool to dump the wifi profiles and cleartext passwords of the connected access points on the Windows machine. This tool will help you in a Wifi penetration testing. Furthermore, it is useful while performing red team or an internal infrastructure engagements.

![Wifi-Dumper](/assets/images/tools/Wifi-Dumper.PNG){: .align-center}

## I-See-You
ISeeYou is a Bash and Javascript tool to find the exact location of the users during social engineering or phishing engagements. Using exact location coordinates an attacker can perform preliminary reconnaissance which will help them in performing further targeted attacks.

![ISeeYou](/assets/images/tools/ISeeYou.PNG){: .align-center}

## Powershell-RAT
Python based backdoor that uses Gmail to exfiltrate data through attachment. This RAT will help during red team engagements to backdoor any Windows machines. It tracks the user activity using screen capture and sends it to an attacker as an e-mail attachment.

![Powershell-RAT](/assets/images/tools/Powershell-RAT.PNG){: .align-center}

## Remote-Desktop-Caching
This tool allows one to recover old RDP (mstsc) session information in the form of broken PNG files. These PNG files allows Red Team member to extract juicy information such as LAPS passwords or any sensitive information on the screen. Blue Team member can reconstruct PNG files to see what an attacker did on a compromised host. It is extremely useful for a forensics team to extract timestamps after an attack on a host to collect evidences and perform further analysis.

![Remote-Desktop-Caching](/assets/images/tools/Remote-Desktop-Caching.PNG){: .align-center}

## In-Spectre-Meltdown
This tool allows to check speculative execution side-channel attacks that affect many modern processors and operating systems designs. CVE-2017-5754 (Meltdown) and CVE-2017-5715 (Spectre) allows unprivileged processes to steal secrets from privileged processes. These attacks present 3 different ways of attacking data protection measures on CPUs enabling attackers to read data they shouldn't be able to. This tool is originally based on Microsoft: https://support.microsoft.com/en-us/help/4073119/protect-against-speculative-execution-side-channel-vulnerabilities-in 

![In-Spectre-Meltdown](/assets/images/tools/In-Spectre-Meltdown.PNG){: .align-center}

## PeekABoo
PeekABoo tool can be used during internal penetration testing when a user needs to enable Remote Desktop on the targeted machine. It uses PowerShell remoting to perform this task.  Note: Remote desktop is disabled by default on all Windows operating systems. 
![PeekABoo](/assets/images/tools/Peek-A-Boo.PNG){: .align-center}

## SMWYG-Show-Me-What-You-Got
This tool allows you to perform OSINT and reconnaissance on an organisation or an individual. It allows one to search 1.4 Billion clear text credentials which was dumped as part of BreachCompilation leak. This database makes finding passwords faster and easier than ever before.
![SMWYG](/assets/images/tools/SMWYG.PNG){: .align-center}

## XposedOrNot
XposedOrNot (XoN) tool is to search an aggregated repository of xposed passwords comprising of ~850 million real time passwords. Usage of such compromised passwords is detrimental to individual account security.
![XposedOrNot](/assets/images/tools/Xposed.PNG){: .align-center}

## HiveJack
HiveJack tool can be used during internal penetration testing to dump Windows credentials from an already-compromised host. It allows one to dump SYSTEM, SECURITY and SAM registry hives and once copied to the attacker machines provides an option to delete these files to clear the trace.

Often, this is a repetitive process, once an attacker gets system-level access on the compromised host dumping hives values is the next step. Time is very valuable when it comes to internal penetration testing. HiveJack will save you plenty of time when it comes to dumping and deleting the files. You'll never have to remember the command to perform the actions.
![HiveJack](/assets/images/tools/HiveJack.PNG)

## Phirautee - Ransomware using Living off the Land (LotL) Tactics
A proof of concept crypto virus to spread user awareness about attacks and implications of ransomwares. Phirautee is written purely using PowerShell and does not require any third-party libraries. This tool steals the information, holds an organisation’s data to hostage for payments or permanently encrypts/deletes the organisation data.

Phirautee is a Living off the Land (LotL) ransomware which means it utilises legit powershell commands and operations to work against the operating system.
![Phirautee](/assets/images/tools/phirautee.png)
{: .align-center}

## BigBountyRecon
BigBountyRecon tool utilises 58 different techniques using various Google dorks and open source tools to expedite the process of initial reconnaissance on the target organisation. Reconnaissance is the most important step in any penetration testing or a bug hunting process. It provides an attacker with some preliminary knowledge on the target organisation. Furthermore, it will be useful to gain insights into what controls are in place as well as some rough estimations on the security maturity level of the target organisation.

This tool can be used in addition to your usual approach for bug hunting. The idea is to quickly check and gather information about your target organisation without investing time and remembering these syntaxes. In addition, it can help you define an approach towards finding some quick wins on the target.
![BigBountyRecon](/assets/images/tools/BBR.PNG)
{: .align-center}

## DDWPasteRecon
Pastesites are websites that allows users to share plain text through public posts called “pastes.”

Once attackers compromise the external perimeter and gain access to the internal resources they release the part of data on the "paste" sites like pastebin or hastebin. As these hackers or malicious groups publish dumps on such sites others users can see sensitive information through paste sites.

With various malicious groups now using these services as communication channels, temporary storage or sharing, and various other sources being used to trade POC code, I thought it would be a good idea to have an easy tool to help organisations Blue and Red Teams to have a visibility into these sites via Google dorks.

DDWPasteRecon tool will help you identify code leak, sensitive files, plaintext passwords, password hashes. It also allow member of SOC & Blue Team to gain situational awareness of the organisation's web exposure on the pastesites. It Utilises Google's indexing of pastesites to gain targeted intelligence of the organisation. Blue & SOC teams can collect and analyse data from these indexed pastesites to better protect against unknown threats.
![DDWPasteRecon](/assets/images/tools/DDW.PNG)
{: .align-center}

