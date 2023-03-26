# <p align="center"> Security Notes</p>


Security is the practice of protecting information and resources from unauthorized access, use, disclosure, disruption, modification, or destruction. 

It involves the implementation of measures to ensure confidentiality, integrity, and availability of information.

There are different types of security, including physical security, network security, and information security. 

**Physical security** involves protecting physical assets, such as buildings, equipment, and personnel, from unauthorized access or damage. 

**Network security** involves protecting computer networks and devices from unauthorized access, use, disclosure, or modification. 

**Information security** involves protecting information and data from unauthorized access, use, disclosure, or modification.


### Key Concepts:

<img width="1097" alt="image" src="https://user-images.githubusercontent.com/124072294/227321640-67727d90-1645-4e47-b7c9-8137edbf1f9a.png">

**Confidentiality:** This means ensuring that information is kept secret and only accessible by authorized individuals.

**Integrity:** This means ensuring that information is accurate and has not been tampered with or modified in any unauthorized way.

**Availability:** This means ensuring that information is available when it is needed, and that it is not subject to denial of service attacks or other disruptions.

**Authentication:** This is the process of verifying the identity of a user, system, or device.

**Authorization:** This is the process of determining what actions a user, system, or device is allowed to perform.

**Encryption:** This is the process of converting information into a secret code or cipher to prevent unauthorized access.

These are just a few of the basic concepts and principles of security.


### The Security Life Cycle consists of: 

**Prevention**

Prevention is the first and arguably the most important phase of the security lifecycle. It offers the opportunity to proactively stop threats from becoming breaches through the implementation of security controls.

• Identify the assets to be protected: You build an inventory of the networking devices, computers, applications, and other physical and digital resources that you must protect.

• Assess asset vulnerability: You examine each asset in the inventory and determine the type and level of protection that the asset needs.

• Implement countermeasures: For each asset to be protected, you implement security controls to prevent attacks against the asset from being successful.


Detection



Response



Analysis

<img width="1173" alt="image" src="https://user-images.githubusercontent.com/124072294/227323187-c60fd72f-af3b-4a27-a4fd-df0f3d826647.png">

### **A comprehensive security strategy for an AWS infrastructure typically includes the following components:**


**Identity and Access Management (IAM):** Implementing IAM controls is crucial to prevent unauthorized access to AWS resources. This includes defining access policies and roles for users, groups, and services, enforcing MFA (multi-factor authentication), and regularly reviewing and auditing access privileges.

**Network Security:** Securing the network is important to prevent attacks such as DDoS and network intrusion. This includes setting up network firewalls, configuring VPCs, and implementing security groups and NACLs (network access control lists).

**Encryption:** Encryption is crucial to protect sensitive data in transit and at rest. This includes using SSL/TLS certificates, encrypting data at rest using AWS KMS (Key Management Service), and encrypting data in transit using VPN and SSL/TLS.

**Monitoring and Logging:** Implementing logging and monitoring tools helps to detect and respond to security incidents quickly. This includes setting up CloudTrail for auditing and logging AWS API calls, and using tools such as Amazon GuardDuty, Amazon Inspector, and AWS Config for threat detection and management.

**Disaster Recovery:** Implementing disaster recovery strategies helps to minimize the impact of security incidents and ensure business continuity. This includes creating backups of critical data and setting up disaster recovery plans and procedures.

**Employee Training:** Employee training is important to raise awareness of security threats and promote best practices. This includes providing regular security awareness training, implementing security policies and procedures, and conducting regular security audits.


### Network Security Threats

A network security threat is any attempt to expose, alter, disable, or gain unauthorized access to an organization’s network. Its purpose is to steal data or perform a malicious activity

It is important to protect networks from discovery tools and mechanisms because of the security risks that these tools present. One of the most effective ways to do so is to block or restrict the use of the discovery protocols that these tools use. 

The most common network discovery tools use the Internet Control Message Protocol (ICMP). For example, the ping and traceroute commands and the Nmap utility use ICMP. Tools that use the Simple Network Management Protocol (SNMP) can also expose detailed network data. 

Network operators typically use them to monitor and manage the devices on a network. If the use of SNMP tools is not securely controlled, attackers can exploit them.

By restricting the use of or disabling network discovery protocols, you can prevent attackers from getting crucial information about your network.

**In the AWS Cloud**
Amazon Inspector scans Amazon Elastic Compute Cloud (Amazon EC2) instances for open network paths and other network reachability issues and provides guidance about restricting access that is not secure


<img width="1187" alt="Screenshot 2023-03-25 at 4 58 55 PM" src="https://user-images.githubusercontent.com/124072294/227741529-0c156923-ab31-4c0e-8661-c39fa1f64c6a.png">

**AWS Network Firewall** is a service that facilitates the deployment of essential network protections to virtual private clouds (VPCs) on AWS. Its IPS provides active traffic flow inspection with real-time network and application layer protections against vulnerability exploits and brute force attacks. Network Firewall uses a signature-based detection engine that matches network traffic patterns to known threat signatures. Its criteria for matching include packet anomalies and packet attributes such as byte sequences.


<img width="1186" alt="image" src="https://user-images.githubusercontent.com/124072294/227741709-34b0c6c5-fb9b-4d0e-bb0b-e1a222ffd923.png">



Network segmentation, also called **subnetting**, is another technique for enhancing the security of a network. Subnetting is the process of taking a large network and dividing it into smaller networks. Each smaller network is called a subnet and is assigned a contiguous subset of the IP address range of the large network. Each subnet can then be secured to meet the specific needs of the resources that it will host. For example, in an organization with multiple office locations, each location might provide a different service and have different security requirements. Therefore, the organization might want to create individual subnets for each location so that they can apply different levels of security to the different subnets.

