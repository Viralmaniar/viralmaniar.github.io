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

  
# Lapsus$ targating Microsoft Exchange Servers:

Lapsus had been focusing on Microsoft Exchange Servers with the aim of seizing control of multiple cloud service-related root accounts. Upon gaining access to these root accounts email addresses, they proceeded to reset the passwords and establish new ones. Notably, there were numerous CVEs identified targeting Microsoft Exchange leading up to full compromise and nuking of the entire infrastructure.  Here are some significant CVEs that threat actors were targating:

    CVE-2021-26855: This was a critical vulnerability in Microsoft Exchange Server that allowed an attacker to execute arbitrary code on the Exchange Server due to improper validation of user-supplied input.

    CVE-2021-26857: Another critical vulnerability in Microsoft Exchange Server that allowed an attacker to run arbitrary code with SYSTEM privileges on the Exchange Server by exploiting a server-side request forgery (SSRF) vulnerability.

    CVE-2021-26858: Similar to CVE-2021-26855, this was a critical vulnerability in Microsoft Exchange Server that allowed an attacker to execute arbitrary code on the Exchange Server due to improper validation of user-supplied input.

    CVE-2021-27065: This was a post-authentication arbitrary file write vulnerability in Microsoft Exchange Server that allowed an attacker to write a file to any path on the server.

    CVE-2021-27078: This vulnerability was in the Exchange Control Panel (ECP) component of Microsoft Exchange Server, allowing an attacker to gain access to arbitrary files on the server.

    CVE-2021-28480: This was a remote code execution vulnerability in Microsoft Exchange Server. Exploiting this vulnerability allowed an attacker to execute arbitrary code in the context of the SYSTEM user.

![0 6gzTzrJoJUaN0UPg](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/6316e83b-3185-4d78-bb6f-cf59fa05eb59)

# Other TTPs for gaining access to the initial account:

## Jenkins: 
If a Jenkins server encounters authentication related misconfigurations, you won't be asked to log in. Instead, visiting the Jenkins server's base URL will show its homepage, usually listing the projects that are available.

![image9](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/d8cad0e8-d616-4a24-9014-52ce13fcd179)

When hunting for initial access Lapsus$ focus is on the Script Console page, found at https://JENKINS_URL/script. This page enables the execution of Groovy script code, which can initiate various operating system commands (Windows/Linux). These commands run with the same permissions as the Jenkins server, typically associated with a highly privileged user base.

For instance, we successfully demonstrated the capability of the Script Console page to execute OS commands such as whoami and ipconfig on a Windows server.

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/54960901-8c4a-41d8-b558-2d0f0a589fd4)

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/6a7c84da-7491-41a6-9f37-67065439a85e)

Another critical area Lapsus$ group examines for authentication problems is the Credentials page, accessible at https://JENKINS_URL/credentials. This page permits access to encrypted credentials, which can potentially be extracted by inspecting the page source.

During my investigation, we encountered a Jenkins server stored multiple AWS credentials, some of which granted complete control over the AWS environment:

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/db472c87-e70b-41d9-b043-d0765740483e)

## Insider Threats:

A disgruntled employee with elevated AWS privileges decides to create havoc before leaving the company. They use AWSNuke to indiscriminately delete critical production resources, including EC2 instances, S3 buckets containing customer data, and RDS databases.

## Compromised Credentials:

Attackers gain access to AWS IAM credentials through phishing or credential stuffing attacks. Upon gaining access, they deploy malicious infrastructure and use AWSNuke to cover their tracks by deleting logs and eliminating evidence of their activities.

## Misconfigured Automation:

A misconfigured automation script inadvertently triggers AWSNuke, intending to clean up all environments mistakenly targeting production resources due to a scripting error.

# Exfilteration and Impact:

The threat actor group Lapsus$ leverages services like Ngrok and FileZilla in a coordinated attack for efficient data exfiltration. 

Ngrok, a tunneling software, could be employed to create a secure connection from the compromised system to an external server controlled by the attackers. By setting up a tunnel, they can bypass firewall restrictions and securely transmit sensitive data, such as stolen credentials or proprietary information, without triggering alarms. 
![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/21f6c633-3f4c-4e47-b0c6-88a96a977d4b)


Additionally, FileZilla, a popular FTP client, could serve as the transfer mechanism to upload exfiltrated files from the compromised system to the attacker's server via the Ngrok tunnel. This combination allows Lapsus$ to stealthily exfiltrate data while evading detection by traditional network monitoring and security measures, posing significant challenges for incident response teams aiming to detect and mitigate such activities promptly.

![8099-d6](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/667f897d-132b-4f84-be2d-70ce08fc0bd2)

The threat actor group Lapsus$ uses Dropbox for covert data exfiltration by leveraging its cloud storage capabilities. They might utilise Dropbox as a repository to upload stolen data, such as sensitive documents, intellectual property, or compromised credentials, using Dropbox's synchronisation feature to seamlessly transfer files from a compromised system to their designated Dropbox account. 

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/46c0b9b9-1ab6-467c-94f3-e302229de396)

