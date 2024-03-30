---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  " Destroying Cloud Infrastructure with Nuking Tools"
date:   2024-01-13 00:18:25 +1000
categories:
  - Offnesive Security
  - Cloud Security
tags:
  - Offensive Security
  - Nuking Tools
  - 
---

Cloud computing has become the backbone of countless businesses, ensuring the security of cloud infrastructure is of utmost importance. Misconfigurations, unused resources, and forgotten deployments can lead to potential vulnerabilities, compliance issues, and unnecessary costs to the business.  In this blog, we'll look at how ransomware groups can mess up a company's cloud security using powerful open-source tools. They do this by targeting insecure resources and nuking the whole setup, putting the organisation at risk.

We'll check out below nuking tools that go after various cloud services:

- AWS-Nuke: https://github.com/rebuy-de/aws-nuke
- Gcp-Nuke: https://github.com/arehmandev/gcp-nuke
- Azure-Nuke: https://github.com/ekristen/azure-nuke
- Cloud Nuke: https://github.com/gruntwork-io/cloud-nuke


# AWS-Nuke:

AWS-Nuke is an open-source tool developed by the team at rebuy.com, a German e-commerce company. It allows users to programmatically delete resources in their Amazon Web Services (AWS) accounts. AWS-Nuke utilises a configuration file to define the resources to be nuked, which makes it highly flexible and customisable.

# Cloud-Nuke:
Cloud-Nuke is another open-source tool developed by Gruntwork. While AWS-Nuke focuses solely on AWS resources, Cloud-Nuke expands the scope to cover multiple cloud providers, including AWS, GCP, and Microsoft Azure. Cloud-Nuke's design philosophy is to provide a unified approach for resource removal across different cloud providers, making it an ideal choice for ransomware group to target an organisation with a multi-cloud infrastructure.

# WARNING!:

All these tools are HIGHLY DESTRUCTIVE and deletes all resources! Be very careful of to use these tools in a production environment!

# Usage:

**- cloud-nuke:**

Simply running `cloud-nuke aws` will start the process of cleaning up your cloud account. You'll be shown a list of resources that'll be deleted as well as a prompt to confirm before any deletion actually takes place.

In AWS, to delete only the default resources, run `cloud-nuke defaults-aws`. This will remove the default VPCs in each region, and will also revoke the ingress and egress rules associated with the default security group in each VPC. Note that the default security group itself is unable to be deleted.



# Lapsus$ Ransomware Group:
Beginning in late 2021 and continuing late into 2022, a globally active, extortion-focused cyber threat actor group attacked dozens of well-known companies and government agencies around the world.

The LAPSUS$ group (referred to as DEV-0357 by Microsoft) is a loose collective of threat actors unassociated with any particular political group or philosophy. The maxim “no honor among thieves” applies to LAPSUS$ members: they have demonstrated themselves to be unprofessional—even by ransomware gang standards—by failing to honor their promises to destroy stolen data.

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/413e4e73-0571-44e8-9d79-bfdce57f2d48)


# How Lapsus$ got Initial Access?

- Password Bruteforce agaist OWA/VPN portals available on the Internet
  
- Redline Stealer is a notorious malware strain that specifically targets well known browsers, aiming to compromise users' sensitive information and credentials. RedLine Stealer is a malware available on underground forums for sale apparently as standalone ($100/$150 depending on the version) or also on a subscription basis ($100/month). This malicious software extracts data from web browsers, including stored login details, autocomplete records, and credit card details. Additionally, when operating on a targeted system, it conducts an inventory that encompasses user-specific data like usernames, location information, hardware specifications, and details about installed security applications.

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/baf9dada-f5d4-46b7-bbb6-61e0a9bad029)


- Accessing browser stored passwords
![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/44a09fd7-4809-4b24-bae3-277f1b3bb07d)

- Running cracked version of applications on the endpoint
![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/fdebd955-723d-477e-847d-6e98d04b983c)

- Through authenticated and long term cookies MFA were bypassed

- MFA fatigue was another reason for the group to gain access to the system after successful bruteforce attempts

  
# Lapsus$ targating Microsoft Exchange 

There were several notable CVEs targeting Microsoft Exchange. Here are some significant ones up to that point:

    CVE-2021-26855: This was a critical vulnerability in Microsoft Exchange Server that allowed an attacker to execute arbitrary code on the Exchange Server due to improper validation of user-supplied input.

    CVE-2021-26857: Another critical vulnerability in Microsoft Exchange Server that allowed an attacker to run arbitrary code with SYSTEM privileges on the Exchange Server by exploiting a server-side request forgery (SSRF) vulnerability.

    CVE-2021-26858: Similar to CVE-2021-26855, this was a critical vulnerability in Microsoft Exchange Server that allowed an attacker to execute arbitrary code on the Exchange Server due to improper validation of user-supplied input.

    CVE-2021-27065: This was a post-authentication arbitrary file write vulnerability in Microsoft Exchange Server that allowed an attacker to write a file to any path on the server.

    CVE-2021-27078: This vulnerability was in the Exchange Control Panel (ECP) component of Microsoft Exchange Server, allowing an attacker to gain access to arbitrary files on the server.

    CVE-2021-28480: This was a remote code execution vulnerability in Microsoft Exchange Server. Exploiting this vulnerability allowed an attacker to execute arbitrary code in the context of the SYSTEM user.






