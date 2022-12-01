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
# Automated Threat Intelligence and Response using TIP and SOAR

# What is a TIP?

Threat Intelligence products and services deliver knowledge, information and data about cybersecurity threats and other cybersecurity-related issues. The output of these products and services aim to provide or assist in the curation of information about the identities, motivations, characteristics and methods of threats, commonly referred to as tactics, techniques and procedures (TTPs). The intent is to enable better decision making and improve security technology capabilities to reduce risk and the chance of being compromised.

By combining threat intelligence with internal telemetry, you can begin to get an understanding of not only what is happening within your network, but can also help you establish a proactive stance and be informed and better prepared for potential threats or blind spots in your defense. 
What is a SOAR?

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




![2](https://user-images.githubusercontent.com/3501170/205014667-a96818ca-5714-47d2-9277-c2dd19b7283e.png)
![3](https://user-images.githubusercontent.com/3501170/205014691-72716815-e71f-4f45-af2c-109449aa7f16.png)
![4](https://user-images.githubusercontent.com/3501170/205014693-ed051fb5-7cee-4123-8534-b2c644108582.png)
![5](https://user-images.githubusercontent.com/3501170/205014739-dcca8238-8007-4d03-a3c5-af5e7548811c.png)
![6](https://user-images.githubusercontent.com/3501170/205014747-8d9e50ab-2388-40b0-a87b-9270a10fe664.png)
![7](https://user-images.githubusercontent.com/3501170/205014750-b0c543f4-210c-4aba-9adb-e6ea8123f8a1.png)
![8](https://user-images.githubusercontent.com/3501170/205014756-ca02e26a-4c81-47d1-a815-c24730537e1c.png)
![9](https://user-images.githubusercontent.com/3501170/205014762-8fc8eb9c-07a9-4d68-8121-2b6b2a6f7d5f.png)
![10](https://user-images.githubusercontent.com/3501170/205014767-5c2a1007-d6ad-41b2-89a3-613c12890050.png)
![11](https://user-images.githubusercontent.com/3501170/205014772-ee1616cb-8d1b-4ba1-957b-f206e3beb418.png)
![12](https://user-images.githubusercontent.com/3501170/205014775-f837ca18-df32-4b6f-9c0b-9b53e12b6ec7.png)
![13](https://user-images.githubusercontent.com/3501170/205014779-aeccf5d7-3bd8-408c-ac05-b79fe0b364d4.png)
![14](https://user-images.githubusercontent.com/3501170/205014783-2afb24a9-6718-41c1-9021-12fb7b59caa4.png)
![15](https://user-images.githubusercontent.com/3501170/205014786-88ab9095-fd6f-44f7-8321-4504aa3e42ee.png)
![16](https://user-images.githubusercontent.com/3501170/205014814-48e3fa53-2164-4681-be37-e3653ad6a5fd.png)
![17](https://user-images.githubusercontent.com/3501170/205014820-17ae14ab-da2a-4f03-a9db-d9e614f0b510.png)
![18](https://user-images.githubusercontent.com/3501170/205014825-550e88b8-447b-4c62-b2af-782776a12c90.png)
![19](https://user-images.githubusercontent.com/3501170/205014829-78ffd4db-3198-46e5-9238-2196bf3aa20b.png)
![20](https://user-images.githubusercontent.com/3501170/205014838-ab9e8913-64ec-4e44-b58d-d1175b75f969.png)
![21](https://user-images.githubusercontent.com/3501170/205014842-19074611-27d3-4204-b0e9-11f88ba3fe84.png)
![22](https://user-images.githubusercontent.com/3501170/205014850-1af0da07-609f-4d91-9598-b3dd41e478e0.png)
![23](https://user-images.githubusercontent.com/3501170/205014857-1be79cf2-2ea5-44b4-a91a-4e9012566b55.png)
![24](https://user-images.githubusercontent.com/3501170/205014866-6ac5d351-8ee9-46da-a40c-ec1e854e4718.png)
![25](https://user-images.githubusercontent.com/3501170/205014874-41fd5cc0-08ca-4735-be85-771bc9385017.png)

