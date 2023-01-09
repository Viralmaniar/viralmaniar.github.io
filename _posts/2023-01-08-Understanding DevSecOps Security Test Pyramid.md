---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Understanding DevSecOps Security Test Pyramid"
date:   2023-01-08 22:14:00 +1000
categories:
  - DevOps
  - Security Automation
  - DevSecOps
tags:
  - DevOps
  - Security Automation
  - DevSecOps
---

Happy New Year, readers! 

I hope you had a wonderful time off with your loved ones during the holiday season. As we begin a new year, let's all strive to make it our best one yet. Here's to a great weekend and an even better year ahead!


There are several options that can address both security and the needs of the delivery team. 

Bottom of the pyramid:

**1. SAST or Unit Tests:** One such option is unit tests or static code analysis tests (also known as static application security testing or SAST). These tests examine source code or compiled code for security vulnerabilities. By fixing any issues identified by these tests before committing code to the source code management tool, we can prevent security problems from reaching the production environment.

Middle layers of the pyramid:

**2. Dependency scanning:** It's important to regularly check third-party and open-source dependencies for vulnerabilities. Security teams often maintain a list of approved dependencies that developers can use when building new features for an application. Performing thorough scans of these dependencies helps ensure that the application remains secure.

**3. Image Scanning:** Image scanning is an essential part of a DevSecOps workflow. It involves analysing Docker images and other types of container images for security vulnerabilities and other issues. By scanning images early in the development process, organisations can identify and address potential problems before they become more serious. Image scanning can also help ensure that only approved images are deployed in production environments. There are several tools available that can automate image scanning, making it easier to incorporate into the development workflow. In addition to scanning images, it's also important to regularly update and patch images to ensure that they are secure and compliant with the organisation's security standards. 

**4. Container Scanning:** By scanning containers and their components security team identify potential security threats. There are several tools available that can automate container scanning, making it easier to incorporate into the development workflow. In addition to scanning containers, it's also important to regularly update and patch containers to ensure that they are secure and compliant with the organisation's security standards.

**5. Network Scanning:** Network scanning consist of examining network infrastructure and devices for vulnerabilities and other security issues. By performing regular network scans, organizations can identify and address potential problems before they become more serious.

There are several tools available for performing network scanning. Some examples include:

- Nmap: This open-source tool is widely used for network discovery and security auditing. It can scan networks for live hosts, open ports, and other information.

- OpenVAS: This open-source tool performs vulnerability assessments and can be used to scan networks for security issues.

By incorporating network scanning into a DevSecOps workflow, organisations can ensure that their networks are secure and compliant. Regular scans can help identify and address potential problems early in the development process, reducing the risk of security incidents and downtime.

In addition to using dedicated scanning tools, organisations can also incorporate network scanning into their continuous integration and delivery (CI/CD) pipeline. This can help ensure that only secure and compliant infrastructure is deployed in production environments.

**6. IAST - Interactive Application Security Testing:**

**7. RASP - Runtime Application Self Protection:**

**8. DAST - Dynamic Application Security Testing:**

Top of the pyramid:

**9. Penetration Testing:**

**10. Bug Bounty Programs:**

**11. Peer Reviews:**


