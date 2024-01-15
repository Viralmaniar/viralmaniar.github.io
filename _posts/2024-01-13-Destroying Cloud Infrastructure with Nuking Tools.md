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


# Lapsus$ Ransomware Group

