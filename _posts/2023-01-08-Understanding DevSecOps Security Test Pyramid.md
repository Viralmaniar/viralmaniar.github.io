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

The security testing pyramid is a concept that helps organisations understand how to balance their testing efforts between different levels of the software development lifecycle. At the top of the pyramid are high-level tests that are typically more expensive and time-consuming to implement, such as penetration testing and other types of security assessments. As you move down the pyramid, the tests become progressively less expensive and more granular, culminating in unit tests and other low-level tests at the bottom.

The security testing pyramid is an important concept in DevSecOps, as it helps organisations understand how to effectively balance the need for thorough testing with the need to control costs. By placing an emphasis on low-level tests, organizations can identify and address potential issues early in the development process, which can help reduce the overall cost of testing and improve the security of their systems.

However, it's important to note that the security testing pyramid is not a one-size-fits-all approach. The specific mix of tests that an organisation uses will depend on a variety of factors, including the complexity of the system being developed, the level of risk involved, and the resources available to the organization. By carefully planning and organizing their testing efforts, organisations can ensure that they are effectively balancing the needs of their specific environment with the overall goals of the DevSecOps process.

In this blog post we will explore the following:

![image](https://user-images.githubusercontent.com/3501170/211244895-af404a5a-8a17-4c7d-9b43-46c221f0cd4f.png)


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

**6. IAST - Interactive Application Security Testing:** IAST is a technique used to identify and address security vulnerabilities in web applications. It involves injecting code into the application to monitor its behavior and identify potential security issues.

IAST is a powerful tool for identifying security issues in web applications. Unlike other testing techniques, such as Static Application Security Testing (SAST) or Dynamic Application Security Testing (DAST), IAST provides real-time visibility into the application's behavior. This makes it particularly effective at identifying issues that may not be detectable through other means.

To perform IAST, a testing tool is typically integrated into the application's runtime environment. This allows the tool to monitor the application's behavior as it is being used. The tool looks for patterns or behaviors that may indicate a security vulnerability, such as input validation issues or cross-site scripting (XSS) attacks. If a potential issue is identified, the tool will generate a report indicating the issue and providing guidance on how to fix it.

IAST is an important part of a DevSecOps workflow. By integrating IAST into the development process, organisations can identify and address security issues early in the development cycle. This helps to reduce the risk of security incidents and improves the overall security posture of the application.

**7. RASP - Runtime Application Self Protection:** RASP is a security technology that helps protect web applications from attacks. It works by integrating security capabilities into the application's runtime environment, allowing it to monitor and protect itself in real-time. 

RASP is designed to be highly effective at detecting and preventing a wide range of attacks, including injection attacks, cross-site scripting (XSS) attacks, and other types of malicious activity. It works by analysing the application's behavior in real-time and identifying patterns or behaviors that may indicate an attack. If an attack is detected, RASP can take a variety of actions to protect the application, such as blocking the attack, alerting security personnel, or logging the incident.

One of the key benefits of RASP is that it provides protection against attacks that may not be detectable through other means. Because it is integrated into the application's runtime environment, RASP has visibility into the application's behavior that is not available to other security technologies. This makes it an effective tool for protecting against zero-day vulnerabilities and other types of unknown threats.

**8. DAST - Dynamic Application Security Testing:** DAST is a technique used to identify security vulnerabilities in web applications. It involves analysing the application's behavior during runtime, typically by simulating attacks and other types of malicious activity.

Unlike Static Application Security Testing (SAST), which analyzes source code to identify vulnerabilities, Dynamic Application Security Testing (DAST) uses the black box testing methodology to assess vulnerabilities from the outside. This means that DAST does not have access to the application's source code, and instead relies on observing the application's behavior during runtime to identify potential issues.

Top of the pyramid: The top of the pyramid is not well integrated into the CI/CD pipeline

**9. Penetration Testing:** Web application penetration testing is a technique used to identify and address security vulnerabilities in web applications. It involves simulating a cyber attack against the application in order to identify weaknesses and assess the application's resilience to such attacks. Pen testing can be an effective way to identify and address vulnerabilities that may not be detectable through other means, such as automated security testing tools. It is typically performed by experienced security professionals who have a deep understanding of different types of attacks and how to identify and exploit vulnerabilities. By conducting regular web application penetration tests, organisations can improve the security of their applications and reduce the risk of security incidents.

**10. Bug Bounty Programs:** A bug bounty program is a way for organisations to incentivise security researchers and other individuals to identify and report security vulnerabilities in various web application products or services. These programs typically offer a reward, or "bounty," to individuals who are able to identify and report valid security issues.

To create a bug bounty program, an organisation should first determine the scope of the program. This might include specific products or services that are covered, as well as any exclusions or limitations. The organisation should also establish clear guidelines for what types of vulnerabilities are eligible for a bounty, and how the bounty will be paid out. It is also important to establish clear communication channels through which researchers can report vulnerabilities, as well as a process for reviewing and triaging reports.

Once the program is established, the organisation should promote it widely to attract the attention of security researchers and other potential participants. This might include making the program known through social media, industry forums, and other channels. It is also a good idea to establish relationships with key individuals and organisations in the security community to help spread the word about the program.

A bug bounty program can be an effective way for organisations to improve the security of their products or services. By incentivising individuals to identify and report vulnerabilities, organisations can proactively address potential security issues and improve the overall security posture of their systems.

**11. Peer Reviews:** Peer reviews are an important part of a DevSecOps workflow, as they can help ensure the quality and security of code being developed. Peer reviews involve having other team members review code before it is merged into the main codebase. This can help identify issues such as bugs, security vulnerabilities, and other problems that may not be detectable through automated testing tools.

Peer reviews can also help improve the overall quality of the codebase by ensuring that code adheres to coding standards and best practices. This can make the code easier to maintain and enhance over time.

In addition to identifying technical issues, peer reviews can also help improve communication and collaboration within the development team. By providing an opportunity for team members to discuss code and share knowledge, peer reviews can help foster a culture of continuous learning and improvement.

Incorporating peer reviews into a DevSecOps workflow can help organisations build and maintain high-quality, secure code. By encouraging team members to review and critique each other's work, organisations can improve the quality and security of their systems and reduce the risk of errors and security incidents.

**Lets talk about Cost:**


To reduce costs, organisations should strive to eliminate duplication in their testing efforts. If a test at a higher level fails, but there is no corresponding test at a lower level, it may be useful to add a lower-level test (such as a unit test) to validate the issue. Once the lower-level test has been successfully implemented and run, the higher-level test can be removed from the testing process. This helps to minimise costs by shifting security tests to the lower levels of the testing pyramid, where they are typically less expensive to implement. By carefully planning and organising their testing efforts, organisations can effectively balance the need for thorough testing with the need to control costs.



