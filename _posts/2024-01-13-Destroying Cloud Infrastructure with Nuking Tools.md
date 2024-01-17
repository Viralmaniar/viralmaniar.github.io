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

# How Lapsus$ got Initial Access?

- Password Bruteforce agaist OWA/VPN portals available on the Internet
- Redline Stealer is a notorious malware strain that specifically targets well known browsers, aiming to compromise users' sensitive information and credentials. RedLine Stealer is a malware available on underground forums for sale apparently as standalone ($100/$150 depending on the version) or also on a subscription basis ($100/month). This malicious software extracts data from web browsers, including stored login details, autocomplete records, and credit card details. Additionally, when operating on a targeted system, it conducts an inventory that encompasses user-specific data like usernames, location information, hardware specifications, and details about installed security applications.

![image](https://gist.github.com/assets/3501170/36e2bc92-5438-4a14-afaf-f6c96a9bf668)





