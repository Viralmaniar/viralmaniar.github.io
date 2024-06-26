---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Destroying Cloud Infrastructure with Nuking Tools - LAPSUS$ Case Study"
date:   2024-01-13 00:18:25 +1000
categories:
  - Offnesive Security
  - Cloud Security
tags:
  - Offensive Security
  - Nuking Tools
  - Purple Team
  - Incident Response
---

![unnamed](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/e13252c6-b1da-4504-9a7c-341148aab8a2)

Cloud computing has become the backbone of countless businesses, ensuring the security of cloud infrastructure is of utmost importance. Misconfigurations, unused resources, and forgotten deployments can lead to potential vulnerabilities, compliance issues, and unnecessary costs to the business.  In this blog, we'll look at how ransomware groups can mess up a company's cloud security using powerful open-source tools. They do this by targeting insecure resources and nuking the whole setup, putting the organisation at risk.

We'll check out below nuking tools that go after various cloud services:

- AWS-Nuke: https://github.com/rebuy-de/aws-nuke
- Gcp-Nuke: https://github.com/arehmandev/gcp-nuke
- Azure-Nuke: https://github.com/ekristen/azure-nuke
- Cloud Nuke: https://github.com/gruntwork-io/cloud-nuke

# ⚠️⚠️⚠️⚠️ WARNING!: ⚠️⚠️⚠️⚠️

All these tools are HIGHLY DESTRUCTIVE and deletes all resources! Be very careful of to use these tools in a production environment!

# AWS-Nuke:

AWS-Nuke is an open-source tool developed by the team at rebuy.com, a German e-commerce company. It allows users to programmatically delete resources in their Amazon Web Services (AWS) accounts. AWS-Nuke utilises a configuration file to define the resources to be nuked, which makes it highly flexible and customisable.

# Cloud-Nuke:
Cloud-Nuke is another open-source tool developed by Gruntwork. While AWS-Nuke focuses solely on AWS resources, Cloud-Nuke expands the scope to cover multiple cloud providers, including AWS, GCP, and Microsoft Azure. Cloud-Nuke's design philosophy is to provide a unified approach for resource removal across different cloud providers, making it an ideal choice for ransomware group to target an organisation with a multi-cloud infrastructure.

## Usage: **cloud-nuke:**

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

# Demoing AWS-Nuke: Incident Response Insight:
From a ransomware perspective, understanding how Lapsus$ might exploit AWS resources to delete them. If attackers gain unauthorised access to organisation AWS account using one of the above listed methods they could potentially deploy and persist malicious resources. AWS Nuke provides a proactive approach to delete all resources swiftly and securely, minimizing the impact of such an attack.

### Installing AWS Nuke
`go get github.com/rebuy-de/aws-nuke`

Alternatively, you can clone the repository and build it manually:
```
git clone https://github.com/rebuy-de/aws-nuke.git
cd aws-nuke
go build
```

### Usage

At first you need to create a config file for aws-nuke. This is a minimal one:
```
regions:
- eu-west-1
- global

account-blocklist:
- "999999999999" # production

accounts:
  "000000000000": {} # aws-nuke-example
```

With this config we can run aws-nuke:

```
$ aws-nuke -c config/nuke-config.yml --profile aws-nuke-example
aws-nuke version v1.0.39.gc2f318f - Fri Jul 28 16:26:41 CEST 2017 - c2f318f37b7d2dec0e646da3d4d05ab5296d5bce

Do you really want to nuke the account with the ID 000000000000 and the alias 'aws-nuke-example'?
Do you want to continue? Enter account alias to continue.
> aws-nuke-example

eu-west-1 - EC2DHCPOption - 'dopt-bf2ec3d8' - would remove
eu-west-1 - EC2Instance - 'i-01b489457a60298dd' - would remove
eu-west-1 - EC2KeyPair - 'test' - would remove
eu-west-1 - EC2NetworkACL - 'acl-6482a303' - cannot delete default VPC
eu-west-1 - EC2RouteTable - 'rtb-ffe91e99' - would remove
eu-west-1 - EC2SecurityGroup - 'sg-220e945a' - cannot delete group 'default'
eu-west-1 - EC2SecurityGroup - 'sg-f20f958a' - would remove
eu-west-1 - EC2Subnet - 'subnet-154d844e' - would remove
eu-west-1 - EC2Volume - 'vol-0ddfb15461a00c3e2' - would remove
eu-west-1 - EC2VPC - 'vpc-c6159fa1' - would remove
eu-west-1 - IAMUserAccessKey - 'my-user -> ABCDEFGHIJKLMNOPQRST' - would remove
eu-west-1 - IAMUserPolicyAttachment - 'my-user -> AdministratorAccess' - [UserName: "my-user", PolicyArn: "arn:aws:iam::aws:policy/AdministratorAccess", PolicyName: "AdministratorAccess"] - would remove
eu-west-1 - IAMUser - 'my-user' - would remove
Scan complete: 13 total, 11 nukeable, 2 filtered.

Would delete these resources. Provide --no-dry-run to actually destroy resources.
```

As we see, aws-nuke only lists all found resources and exits. This is because the --no-dry-run flag is missing. Also it wants to delete the administrator. We don't want to do this, because we use this user to access our account. Therefore we have to extend the config so it ignores this user:

```
regions:
- eu-west-1

account-blocklist:
- "999999999999" # production

accounts:
  "000000000000": # aws-nuke-example
    filters:
      IAMUser:
      - "my-user"
      IAMUserPolicyAttachment:
      - "my-user -> AdministratorAccess"
      IAMUserAccessKey:
      - "my-user -> ABCDEFGHIJKLMNOPQRST"
```
```
$ aws-nuke -c config/nuke-config.yml --profile aws-nuke-example --no-dry-run
aws-nuke version v1.0.39.gc2f318f - Fri Jul 28 16:26:41 CEST 2017 - c2f318f37b7d2dec0e646da3d4d05ab5296d5bce

Do you really want to nuke the account with the ID 000000000000 and the alias 'aws-nuke-example'?
Do you want to continue? Enter account alias to continue.
> aws-nuke-example

eu-west-1 - EC2DHCPOption - 'dopt-bf2ec3d8' - would remove
eu-west-1 - EC2Instance - 'i-01b489457a60298dd' - would remove
eu-west-1 - EC2KeyPair - 'test' - would remove
eu-west-1 - EC2NetworkACL - 'acl-6482a303' - cannot delete default VPC
eu-west-1 - EC2RouteTable - 'rtb-ffe91e99' - would remove
eu-west-1 - EC2SecurityGroup - 'sg-220e945a' - cannot delete group 'default'
eu-west-1 - EC2SecurityGroup - 'sg-f20f958a' - would remove
eu-west-1 - EC2Subnet - 'subnet-154d844e' - would remove
eu-west-1 - EC2Volume - 'vol-0ddfb15461a00c3e2' - would remove
eu-west-1 - EC2VPC - 'vpc-c6159fa1' - would remove
eu-west-1 - IAMUserAccessKey - 'my-user -> ABCDEFGHIJKLMNOPQRST' - filtered by config
eu-west-1 - IAMUserPolicyAttachment - 'my-user -> AdministratorAccess' - [UserName: "my-user", PolicyArn: "arn:aws:iam::aws:policy/AdministratorAccess", PolicyName: "AdministratorAccess"] - would remove
eu-west-1 - IAMUser - 'my-user' - filtered by config
Scan complete: 13 total, 8 nukeable, 5 filtered.

Do you really want to nuke these resources on the account with the ID 000000000000 and the alias 'aws-nuke-example'?
Do you want to continue? Enter account alias to continue.
> aws-nuke-example

eu-west-1 - EC2DHCPOption - 'dopt-bf2ec3d8' - failed
eu-west-1 - EC2Instance - 'i-01b489457a60298dd' - triggered remove
eu-west-1 - EC2KeyPair - 'test' - triggered remove
eu-west-1 - EC2RouteTable - 'rtb-ffe91e99' - failed
eu-west-1 - EC2SecurityGroup - 'sg-f20f958a' - failed
eu-west-1 - EC2Subnet - 'subnet-154d844e' - failed
eu-west-1 - EC2Volume - 'vol-0ddfb15461a00c3e2' - failed
eu-west-1 - EC2VPC - 'vpc-c6159fa1' - failed
eu-west-1 - S3Object - 's3://rebuy-terraform-state-138758637120/run-terraform.lock' - triggered remove

Removal requested: 2 waiting, 6 failed, 5 skipped, 0 finished

eu-west-1 - EC2DHCPOption - 'dopt-bf2ec3d8' - failed
eu-west-1 - EC2Instance - 'i-01b489457a60298dd' - waiting
eu-west-1 - EC2KeyPair - 'test' - removed
eu-west-1 - EC2RouteTable - 'rtb-ffe91e99' - failed
eu-west-1 - EC2SecurityGroup - 'sg-f20f958a' - failed
eu-west-1 - EC2Subnet - 'subnet-154d844e' - failed
eu-west-1 - EC2Volume - 'vol-0ddfb15461a00c3e2' - failed
eu-west-1 - EC2VPC - 'vpc-c6159fa1' - failed

Removal requested: 1 waiting, 6 failed, 5 skipped, 1 finished

--- truncating long output ---
```

As you see aws-nuke now tries to delete all resources which aren't filtered, without caring about the dependencies between them. This results in API errors which can be ignored. These errors are shown at the end of the aws-nuke run, if they keep to appear.

`aws-nuke` retries deleting all resources until all specified ones are deleted or until there are only resources with errors left.

## Detection
Anomaly detection systems, monitoring tools or even manual checks may alert to unauthorised access or suspicious activities within cloud account.

## Containment
Once an incident is confirmed containment measures are critical to prevent further damage or unauthorised access.

## Eradication
After containment the focus shifts to complete eradication of compromised resources. 

## Recovery and Remediation
Post-incident, recovery efforts involve rebuilding affected resources and restoring functionality. 

# Lessons Learned from Lapsus$ Ransomware Group

## Attribution is hard

Attribution in cybersecurity incidents, especially with sophisticated threat actors like Lapsus$, proves challenging due to several factors:<BR>
**1. TTPs Overlap:** TTPs often overlap among different threat actor groups, making it difficult to pinpoint specific groups based solely on attack methods.<BR>
**2. Alliances/Affiliations/Splits:** Threat actors may form alliances, have affiliations with other groups or splitinto new entities further complicating attribution efforts.<BR>
**3. Misdirection:** Threat actors like Lapsus$ may employ tactics to mislead investigators such as using false flags or infrastructure leased from third parties.<BR>

## Threat Intelligence is key during Incident Responses

Effective incident response relies heavily on timely and accurate threat intelligence:<BR>
**1. Early Detection**: Access to up-to-date threat intelligence helps in early detection of threats and malicious activities associated with groups like Lapsus$, enabling rapid response.<BR>
**2. Trend Analysis:** Continuous monitoring and analysis of threat intelligence allow organizations to understand evolving tactics and adjust defenses accordingly.<BR>
**3. Attribution Aid:** Comprehensive threat intelligence enhances attribution capabilities by correlating observed TTPs with known threat actor behaviors.<BR>

## Take care of the weakest link: Humans

Human factors remain a critical vulnerability in cybersecurity:<BR>
**1. Phishing Awareness:** Lapsus$ and similar groups often exploit human vulnerabilities through phishing attacks to gain initial access or escalate privileges.<BR>
**2. Training and Education:** Regular cybersecurity training and awareness programs are essential to mitigate the risk of insider threats or inadvertent security breaches.<BR>
**3. Security Culture:** Fostering a security-conscious organisational culture reinforces the importance of adhering to policies and recognising potential threats posed by sophisticated threat actors.<BR>

## Cloud is great, but you need to configure appropriately

While cloud services offer scalability and flexibility, improper configurations can expose organisations to significant risks:<BR>
**1. Misconfigurations:** Lapsus$ has exploited misconfigured cloud environments to gain unauthorised access, exfiltrate data, or deploy ransomware.<BR>
**2. Security Best Practices:** Implementing robust access controls, encryption, and continuous monitoring are crucial to secure cloud infrastructure against evolving threats.<BR>
**3. Compliance and Auditing:** Regular audits and adherence to security best practices help ensure that cloud environments remain resilient against sophisticated threat actors.<BR>

## Unpredictable threat actors can be dangerous

The unpredictability of threat actors like Lapsus$ poses significant challenges:<BR>
**1. Agility in Tactics:** Lapsus$ has demonstrated the ability to quickly adapt tactics and techniques, making them difficult to anticipate or defend against.<BR>
**2. Impact of Attacks:** Their unpredictable nature can lead to widespread disruption, financial loss, and reputational damage for targeted organisations.<BR>
**3. Resilience and Preparedness:** Building resilience through proactive security measures, incident response planning, and threat modeling is essential to mitigate the impact of unpredictable threat actors.<BR>
