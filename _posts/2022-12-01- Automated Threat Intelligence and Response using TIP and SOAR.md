---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Automated Threat Intelligence and Response using TIP and SOAR"
date:   2022-12-1 00:04:00 +1000
categories:
  - Threat Intelligence
  - Security Automation
tags:
  - TIP
  - SOAR
---

# What is a TIP?

Threat Intelligence products and services deliver knowledge, information and data about cybersecurity threats and other cybersecurity-related issues. The output of these products and services aim to provide or assist in the curation of information about the identities, motivations, characteristics and methods of threats, commonly referred to as tactics, techniques and procedures (TTPs). The intent is to enable better decision making and improve security technology capabilities to reduce risk and the chance of being compromised.

By combining threat intelligence with internal telemetry, you can begin to get an understanding of not only what is happening within your network, but can also help you establish a proactive stance and be informed and better prepared for potential threats or blind spots in your defense. 

# What is a SOAR?

Gartner defines SOAR as solutions that combine incident response, orchestration and automation, and threat intelligence platform management capabilities in a single solution. SOAR tools can be used for many security operations tasks, including: 

    - To document and implement processes.
    - To support security incident management. 
    - To apply machine-based assistance to human security analysts and operators. 
    - To better operationalise the use of threat intelligence. 

Workflows can be orchestrated via integrations with other technologies, and automated to achieve desired outcomes — example use cases include: - Incident triage. - Incident response. - Threat intelligence (TI) acquisition curation, management and dissemination based on type of content, role, location and specific areas of interest of the recipients.

Before we jump into some of the use-cases of how we can automate let's look at the type of intelligence.

# Types of Cyber Threat Intelligence

Cyber threat intelligence comes in many forms but can largely be divided into human and machine-readable threat intelligence types.

    - Strategic Threat Intelligence: High level information on changing risks
    - Tactical Threat Intelligence: Attackers Tools, Techniques and Procedures
    - Technical Threat Intelligence: Indicator of Compromise (IOCs)
    - Operational Threat Intelligence: Details of Specific Attack, Member and Intel Sharing

Following diagram shows details of human readable vs machine readable threat intelligence types in detail:
![image](https://user-images.githubusercontent.com/3501170/205014442-396780f7-1b96-4c51-bd96-947bdb857670.png)

 Now that we looked at what TIP, SOAR and types of threat intelligence, we will explore some use-cases to perform automated threat response:

    1. Credential Dumping 
    2. Brute Force Attempts
    3. Ransomware Alert and Analysis

Let’s explore each of these incidents: 

# Automated Protection against Credential Dumping

In this use-case we will try to attack a Windows end-point with Mimikatz to perform credential dumping attack that will extract password hashes and plaintext to further gain control in the network. The end-point is running a Taegis XDR to collect logs. The Cyber Fusion platform will receive an automated alert from Taegis on the Mimikatz activities. Lastly from the automated threat response perspective the Cyber Fusion platform will isolate the Windows host from the network to prevent lateral movement and further compromise of the end-point. 

![2](https://user-images.githubusercontent.com/3501170/205014667-a96818ca-5714-47d2-9277-c2dd19b7283e.png)

Let’s run Mimikatz on the end-point: 

![3](https://user-images.githubusercontent.com/3501170/205014691-72716815-e71f-4f45-af2c-109449aa7f16.png)

An alert is now created in the Taegis XDR via Red Cloak agent as shown below: 

![4](https://user-images.githubusercontent.com/3501170/205014693-ed051fb5-7cee-4123-8534-b2c644108582.png)

Now from an automated actioning perspective a playbook from the Cyber Fusion platform is initiated that will isolate the client from the network: 
 
![5](https://user-images.githubusercontent.com/3501170/205014739-dcca8238-8007-4d03-a3c5-af5e7548811c.png)

As the playbook has been triggered successfully we can see the result on our Windows end point: 
 
 
![6](https://user-images.githubusercontent.com/3501170/205014747-8d9e50ab-2388-40b0-a87b-9270a10fe664.png)

By automating the response against complex and diverse threats, playbooks prove to be effective at minimising response time thereby reducing overall risk exposure.

# Automated Protection against Active Directory Password Bruteforce Attempts

A bruteforce attack uses a password list, which contains the credentials that can be used to bruteforce service logins. This attack automatically and systematically attempts to guess the correct username and password combination for a service. Its goal is to find valid logins and leverage them to gain access to a network. 

Following are the common types of brute force attacks:

    - Dictionary attacks
    - Hybrid bruteforce attacks
    - Password spray attacks 
    - Default password bruteforce attempts

For this use-case we will perform a bruteforce attempt against a domain joined Windows box which has remote desktop service (port 3389) exposed. The Windows end-point is running an Elastic agent which sends logs to SIEM. SIEM will collect Windows events related logs centrally in a separate server. Elastic SIEM will harness data at cloud speed and scale which will allow one to heighten host visibility and control. From a threat response perspective, the Cyber Fusion platform will create an incident ticket with all relevant information in the threat response platform for analysts to triage this event. 

Additionally, the platform will automatically disable the user account to stop the attack and will also block the source FQDN on the firewall. 
![7](https://user-images.githubusercontent.com/3501170/205014750-b0c543f4-210c-4aba-9adb-e6ea8123f8a1.png)

Let’s look at the account status before performing the brute force attack to check if the account is active: 
 
![8](https://user-images.githubusercontent.com/3501170/205014756-ca02e26a-4c81-47d1-a815-c24730537e1c.png)

Connecting to an end-point with an exposed RDP port: 
 
![9](https://user-images.githubusercontent.com/3501170/205014762-8fc8eb9c-07a9-4d68-8121-2b6b2a6f7d5f.png)

Trying a login attempt on a domain user with a common password:

![10](https://user-images.githubusercontent.com/3501170/205014767-5c2a1007-d6ad-41b2-89a3-613c12890050.png)

Multiple login attempts are made against the endpoint as seen in the below screenshot - The login attempt failed:

![11](https://user-images.githubusercontent.com/3501170/205014772-ee1616cb-8d1b-4ba1-957b-f206e3beb418.png)

Alerts have been raised in the Elastic SIEM:

![12](https://user-images.githubusercontent.com/3501170/205014775-f837ca18-df32-4b6f-9c0b-9b53e12b6ec7.png)

An automated playbook is initiated to log an incident:

![13](https://user-images.githubusercontent.com/3501170/205014779-aeccf5d7-3bd8-408c-ac05-b79fe0b364d4.png)

Once the playbook finishes running it will create an incident for the analyst to perform further investigation:

![14](https://user-images.githubusercontent.com/3501170/205014783-2afb24a9-6718-41c1-9021-12fb7b59caa4.png)

Looking at the detection analysis tab:

![15](https://user-images.githubusercontent.com/3501170/205014786-88ab9095-fd6f-44f7-8321-4504aa3e42ee.png)

Once the tickets been created we look at the account status:

![16](https://user-images.githubusercontent.com/3501170/205014814-48e3fa53-2164-4681-be37-e3653ad6a5fd.png)

Logging into the Fortigate Firewall to check the policy:
![17](https://user-images.githubusercontent.com/3501170/205014820-17ae14ab-da2a-4f03-a9db-d9e614f0b510.png)

![18](https://user-images.githubusercontent.com/3501170/205014825-550e88b8-447b-4c62-b2af-782776a12c90.png)

By automatically detecting bruteforce login attempts organisations can quickly detect and respond to possible attacks that are underway and rectify them before the attack succeeds.

# Automated Protection against Ransomware and Malware

Ransomware attacks have grown in numbers and severity over the last few years. The average cost and downtime due to ransomware attacks have also been on the rise. Without implementing adequate detection and response measures, organisations can end up losing access to their valuable data and even incur damages to their reputation in cases of stolen data being leaked by threat actors.

Ransomware operators typically design their exploits to spread laterally across an organisation’s network in an attempt on as many devices as possible from a single execution. has proven to be an effective solution for containing such attacks in their early stages. 

For this use-case we will run a wannacry ransomware binary file on the Windows box to spread the ransomware laterally to infect and encrypt data . The Windows end-point is running an Elastic agent which sends logs to SIEM. SIEM will collect Windows events related logs centrally in a separate server. From an automated playbook-driven response process, the Cyber Fusion platform will create an incident ticket with all relevant information on the binary file from VirusTotal and Hybrid Analysis for enrichment to fetch malware hash reputation in the threat response platform for analysts to triage this event. 

Additionally, the platform will automatically queries Active Directory for fetching more information on the impacted user. 

![19](https://user-images.githubusercontent.com/3501170/205014829-78ffd4db-3198-46e5-9238-2196bf3aa20b.png)

Let’s run a Wannacry binary file on one of the Windows end-points: 

![20](https://user-images.githubusercontent.com/3501170/205014838-ab9e8913-64ec-4e44-b58d-d1175b75f969.png)

Ransomware execution was detected on the end-point: 

![21](https://user-images.githubusercontent.com/3501170/205014842-19074611-27d3-4204-b0e9-11f88ba3fe84.png)

Alerts have been raised in the Elastic SIEM: 

![22](https://user-images.githubusercontent.com/3501170/205014850-1af0da07-609f-4d91-9598-b3dd41e478e0.png)

An automated playbook is initiated to log an incident:

![23](https://user-images.githubusercontent.com/3501170/205014857-1be79cf2-2ea5-44b4-a91a-4e9012566b55.png)

An incident ticket is now created for an analyst with all relevant information on the binary file from VirusTotal and Hybrid Analysis as an enrichment to have context around the incident for further investigation:

![24](https://user-images.githubusercontent.com/3501170/205014866-6ac5d351-8ee9-46da-a40c-ec1e854e4718.png)

Malware hash successfully submitted to the Fortigate firewall: 

![25](https://user-images.githubusercontent.com/3501170/205014874-41fd5cc0-08ca-4735-be85-771bc9385017.png)



# Conclusion:

Cyberattacks can cause severe damage to the data and intellectual property of an organisation. Hence an automated playbook plays an important role in countering the threat at machine speed instead of relying on slower, manual processes.

Additionally automation can help organisations to reduce both Mean Time to Detect (MTTD) and Mean Time to Respond (MTTR) by validating and remediating security alerts within minutes. 
