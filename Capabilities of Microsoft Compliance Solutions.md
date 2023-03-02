# Describe basic security capabilities in Azure
## Describe Azure DDoS protection
### What is a DDoS Attack? 
Distributed Denial of Service Attacks
The goal of a DDoS attack is to overwhelm the resources on apps and servers, making them unresponsive or slow for legitimate users. These attacks usually target any public-facing device that can be access through the internet.

Volumetric attacks
- These are volume-based attacks that flood the network with traffic that appears legitimate but overwhelms the available bandwidth. 
- Legit traffic cannot get through when these attacks occur.
- Measured in bits per second.

Protocol attacks
- These attacks render a target inaccessible by exhausting server resources with fake protocol requests that exploit weaknesses in layer 3 (network) and layer 4 (transport) protocols.
- Measured in packets per second.

Resource (application) layer attacks
- These attacks target web app packets with the purpose of distrupting transmission of data between hosts.

### What is Azure DDoS Protection?
This service is designed to protect apps and servers against network traffic that resembles a DDoS attack.

![Alt text](https://learn.microsoft.com/en-us/training/wwl-sci/describe-basic-security-capabilities-azure/media/2-network-flow.png)

Above, Aure DDoS Protection identifies an attacker's attempt to overwhelm the network then blocks traffic from the attacker to ensure it doesn't reach Azure resources. Legitimate traffic from customers is allowed to access Azure resources without interrupting service.

Azure DDoS Protection uses the scale and elasticity of Microsoft's global network to bring DDoS mitigation capacity to **EVERY** Azure region. Azure can scale an org's computing needs to meet demand during a DDoS attack. 

There are **three** tiers of Azure DDoS Protection:
Default DDoS infrastructure protection
- Previously referred to as Basic.
- Automatically enabled for every property in Azure at no additional cost.
- Always-on traffic monitoring & real-time mitigation of common network-level attacks providing the same defenses that Microsoft's online services use.
- Azure's global network is used to distribute & mitigate attack traffic across regions.

DDoS Network Protection
- Available as a SKU.
- Combined with application design best practices to provide enhaned DDoS mitigation features intended to defend against DDoS attacks.
- Automatically tuned to help protect specified Azure resources within a virtual network.
- Simple to enable on new or existing virtual networks without requiring application or resource changes.
- Advantages over the default; logging, alerting, and telemetry.

DDoS IP Protection (in preview)
- Pay-per-protected IP model.
- Contains the same core engineering features as DDoS Network protection, but differs in DDoS rapid response support, cost protection, & discounts on WAF.

## Describe Azure Firewall
A managed, cloud-based network security service that protects the Azure virtual network (VNet) resources from attackers.
- Can be deployed on **any** virtual network but best practice is to use it on a centralized virtual network.
- All network traffic, virtual or on-prem, will be routed through it.
- The advantage of this service is its ability to centrally exert control of network traffic for **all** VNets across different subscriptions.

Azure Firewall is scalable, allowing you to accomodate changing network traffic flows. This means you don't need a budget for peak traffic. All network traffic will be subjected to the configured firewall rules when routed to the firewall as the subnet default gateway.

### Key Features of Azure Firewall
Built-in high availability & availability zones
- Requires no configuration
- Azure Firewall can be configured to span multiple availability zones for increased availability

Network & application level filtering
- Use IP address, port, and protocol to support fully qualified domain name filtering for outbound HTTP/HTTPS traffic & network filtering controls.

Outbound SNAT & inbound DNAT to communicate with internet resources
- Source Network Address Translation (SNAT) translates the private IP address of network resources to an Azure public IP address to identify & allow traffic originating from the VNet to internet destinations.
- Destination Network Address Translation (DNAT) translates inbound internet traffic to the firewall public IP address, then filters to the private IP addresses of resources on the VNet.

Multiple public IP addresses
- These addresses can be associated with Azure Firewall.

Threat intelligence
- Threat intelligence-based filtering can be enabled for firewall alerts & to deny traffic from/to known malicious IP address and domains.

Integration with Azure Monitor
- Enables collecting, analyzing, and acting on telemetry from Azure Firewall logs when integrated with Azure Monitor.


## Describe Web Application Firewall
Web Application Firewall (WAF) provides centralized protection of web apps from common exploits and vulnerabilities. 
- Helps simplify security management.
- Improves response time to security threats.
- Allows patching known vulnerabilities in one place, instead of having to secure each individal web app.
- Provides application admins better assurance of protection against threats & intrusions.


## Describe Network Segmentation with Azure Virtual Networks
Network segmentation supports the zero trust model & defense in depth.
- Assume breach is a principle of the zero trust model. Having the ability to contain an attacker is crucial to protect information systems.

Network segmentation helps with
- Providing a way to group related assets that are part of, or support, workload operations.
- Isolating resources.
- Setting governance policies.

Placing workloads, or parts of a specific workload, allows you to control traffic from/to those segements to secure communication paths. If one segement is compromised, you'll be able to prevent lateral movement from allowing the compromise to affect the rest of the network.

Network segmentation can also secure interactions between perimeters. This can strengthen an org's security posture, contain risks when a breach occurs, and prevent attackers from gaining access to the entire workload.


## Describe Azure Network Security groups

## Describe Azure Bastion and JIT Access
### Azure Bastion
Azure Bastion is a service you deploy that allows you to connect to VMs using your browser and the Azure portal. It's a fully platform-managed PaaS service that you provision inside your virtual network. 
- Provides secure & seamless RDP & SSH connectivity using TLS.
- VMs don't need a public IP address or special client software.

![Alt text](https://learn.microsoft.com/en-us/training/wwl-sci/describe-basic-security-capabilities-azure/media/2-azure-bastion.png)

Azure Bastion is deployed per virtual network, with support for virtual network peering.

### Key features of Azure Bastion
- RDP & SSH: Connect from the Azure Portal using a single-click.
- Remote session over TLS & firewall traversal for RDP/SSH: Connecting will occur in the web browser and is secured by using TLS to establish encryption.
- No Public IP required on the Azure VM: Azure Bastion opens the RDP/SSH connection to the VM using private IP on the VM.
- No hassle managing NSGs: There is no need to apply any NSGs on an Azure Bastion subnet as the platform is a fully managed PaaS solution that is hardened internally to provide a secure connection.
- Protection against port scanning: VMs are protected against external port scanning as they are not exposed to the internet.
- Hardening in one place to protect against zero-day exploits: Azure Bastion sits at the perimeter of your virtual network so eah VM on the virtual network doesn't need to be hardened individually. Azure protects against zero-days by keeping Azure Bastion hardened and updated.

### JIT Access
Just in Time Access provides the ability to lock down inbound traffic to VMs, reducing the overall exposure to attacks while providing easy access to connect when needed.

After enabling JIT, you can select the ports to block inbound traffic on. Microsoft Defender for Cloud ensures "deny all inbound traffic" rules exist for the selected ports in the NSG and Azure Firewall rules, which restrict access to your Azure VMs' management ports and defend them from attacks.

Note: If other rules exist for these ports, those rules take priority over the new "deny all inbound traffic" rules, otherwise, the new rules take priority in the NSG & Azure Firewall.

### How JIT Access Works
When a user requests to access a VM, Defender for Cloud checks that the user has Azure RBAC permissions for the specific VM. 
- If the request is approved, Defender for Cloud configures the NSGs and Azure Firewall to allow inbound traffic to the selected ports from the relevant IP address, or range, for the specified amount of time. 
- Once the time expires, Defender for Cloud restores the NSGs to their previous states.

Note: Connections that are already established are NOT interrupted.

JIT requires Microsoft Defender for servers to be enabled on the subscription.


## Describe ways Azure encrypts data
Azure Storage Service Encryption
- Helps to protect data at rest.
- Automatically encrypts the data before persisting to Azure-managed disks, Azure Blob Storage, Azure Files, or Azure Queue Storage.
- Decrypts the data before retrieval.

Azure Disk Encryption
- Helps encrypt Windows & Linux IaaS VM disks.
- Uses industry-standard BitLocker feature of Windows & dm-crypt feature of Linux to provide volume encryption for the OS & data disks.

Transparent Data Encryption (TDE)
- Helps protect Azure SQL Database & Azure Data Warehouse against the threat of malicious activity.
- Performs real-time encryption & decryption of the database, backups, and transaction log files at rest without requiring changes to the application.

### Azure Key Vault
A centralized cloud service for storing application secrets. 
- Secrets management: securely store and control access to tokens, passwords, certificates, API keys, and other secrets.
- Key management: allows for easier management of encryption keys.
- Certificate management: Key Vault lets you provision, manage, and deploy public & private SSL/TLS certificates for Azure and internally connected resources more easily.
- Store secrets backed by hardware security modules (HSMs): secrets and keys can be protected by software of FIPS 140-2 Level 2 validated HSMs.


# Describe security management capabilities of Azure
## Describe Cloud security posture management (CSPM)
CSPM: Cloud Security Posture Management

- Free tier includes CSPM features such as secure score, detection of security misconfigurations in your Azure workloads, and asset inventory.

CSPM uses a combination of tools & services:
Zero Trust-based access control
- Considers the active threat level when determining access control.

Real-time risk scoring
- Provides visibility to the top risks

Threat & vulnerability management (TVM)
- Provides a full picture of an orgs attack surface & risk while integrating it into operations & engineering decision-making.

Discover risks
- Provides an understanding of the data exposure of enterprise IP, on sanctioned & unsanctioned cloud services.

Technical policy
- Applies guardrails to audit & enforce the org's standards and applies policies to technical systems.

Threat modeling systems & architectures
- Used alongside other applications.

CWPP: Cloud Workload Protection Platform

- Brings a range of security features for advanced, intelligent, protection of your Azure & hybrid resources & workloads. 

Protects the following workloads:

- Servers
- App Service
- Storage
- SQL
- Kubernetes
- ACR
- Key Vault
- Resource Manager
- DNS
- Open-source Azure DB

## Describe Microsoft Defender for Cloud
Defender for Cloud is a tool for security posture management & threat protection. It strengthens the security posture of cloud resources and protects workloads running in Azure, hybrid, and other cloud platforms.

- Continuously assess: know your security posture, identify & track vulnerabilities.
- Secure: harden all connected resources & services.
- Defend: detect & resolve threats to resources, workloads, and services.

The features that deliver these requirements, cover two broad pillars of cloud security:
### Cloud Security Posture Management
- CSPM in Microsoft Defender provides:
- Visibility: helps you understand the current security situation.
- Hardening guidance: helps you efficiently & effectively improve your security.

![Alt text](https://learn.microsoft.com/en-us/training/wwl-sci/describe-security-management-capabilities-of-azure/media/3-security-center-recommendations.png)

### Cloud Workload Protection (CWP)
Microsoft Defender for Cloud is able to detect & resolve threats to resources, workloads, and services. Protections are delivered through integrated Defender plans, specific to the type of resources in an org's subscriptions and provides enhanced security features for the workloads.

## Describe the enhanced security features of Microsoft Defender for Cloud

## Describe security baselines for Azure
Security baselines are standardized documents for Azure product offerings, describing the available security capabilities and the optimal security configurations to help you strengthen security through improved tooling, tracking, and security features. 

Security baselines for Azure focus on cloud-centric control areas in Azure environments. These controls are consistent with well-known industry standards such as: Center for Internet Security (CIS) or National Institute for Standards in Technology (NIST).

NOTE: Microsoft cloud security benchmark is the successor of Azure Security Benchmark (ASB), which was rebranded in October 2022. It's currently in preview.

### Microsoft Cloud Security Benchmark
This feature provides best practices and recommendations to help improve the security of workloads, data, and services in Azure and multicloud environments. Using security benchmarks can help orgs secure cloud deployments & reduce risk in the org in a timely manner.

The best way to understand the Microsoft Cloud Security Benchmark is to view it on GitHub [https://github.com/MicrosoftDocs/SecurityBenchmarks/blob/master/Azure%20Security%20Benchmark/Microsoft_cloud_security_benchmark_v1_preview.xlsx](https://github.com/MicrosoftDocs/SecurityBenchmarks)

Important pieces of the information in MCSB v1 are:
- ID
- Control domain
- Mapping to industry frameworks
- Recommendation
- Security principle
- Azure Guidance
- AWS Guidance

Microsoft Defender for Cloud continuously assesses an org's hybrid cloud environment to analyze the risk factors according to the best practices in the MCSB. Some of the controls used in the benchmark include:
- Network Security
- Identity & Access Control
- Data Protection
- Data Recovery
- Incident Response


### Security Baselines for Azure
Security baselines are standardized documents for Azure products, describing the available security capabilities & the optimal security configs to help strengthen security through improved tooling, tracking, and security features. Service baselines are only available for Azure currently.

Content in the security baseline is grouped by the control domains defined by the MCSB that are applicable to the specific service. A security baseline includes the following info for each applicable MCSB reccomendation:
- Control ID
- Feature
- Feature Description
- Supported
- Enabled by Default
- Configuration Responsibility
- Configuration Guidance
- Microsoft Defender for Cloud monitoring note
- Reference

From Azure Key Vault security baseline: 
![Alt text](https://learn.microsoft.com/en-us/training/wwl-sci/describe-security-management-capabilities-of-azure/media/security-baseline-expanded.png#lightbox)

# Describe security capabilities of Microsoft Sentinel
## Define the concepts of SIEM and SOAR
SIEM: Security Information Event Management
 
- System that collects data from many other sources within the network. 
- Provides real-time monitoring, analysis, correlation & notification of potential attacks

SOAR: Security Orchestration Automation & Response

- Centralized alert and response automation with threat-specific playbooks. 
- Response may be fully automated of single-click. 

## Describe how Microsoft Sentinel provides integrated threat management
Sentinel delivers both SIEM & SOAR together. 

- Uses AI, ML, and threat intel. 
- Provides visibility and context across silos, including apps, identities, endpoints, and data. 
- Provides better context into the scope of thr security incident. 

# Describe threat protection with Microsoft 365 Defender
XDR: Extended Detect & Response

- Uses AI, ML, and threat intel. 
- Refers to the scope & context of investigation & hunting. 

## Describe Microsoft 365 Defender services 
## Describe Microsoft Defender for Office 365

- Formerly called Office 365 Advanced Threat Protection. 
- Safeguards the org against malicious threats in email, URLs, and collaboration tools. 
- Includes Safe Links and Safe Attachments for detonation of potentially malicious email content. 
- Anti-phishing protection & attack simulation. 

## Describe Microsoft Defender for Endpoint

- Formerly called Microsoft Defender Advanced Threat Protection (MDATP). 
- An enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.
- Includes EDR, attack surface reduction, automated investigations, and advanced hunting.   
- Sensor built into Windows 10

## Describe Microsoft Defender for Cloud Apps

- A Cloud Access Security Broker (CASB) designed to detect and stop shadow IT. 
- Provides visibility over data travel and analytics to identify threats over MS & 3rd party cloud services. 
- Natively integrates with multiple other Microsoft services & solutions.

## Describe Microsoft Defender for Identity

- Formerly called Azure Advanced Threat Protection (ATP). 
- Cloud-based security solution that leverages your on-prem AD signals. 
- Identifies, detects, and investigates advanced threats, compromised identities, and malicious insider actions. 
- Requires AD DS. 

## Describe the Microsoft 365 Defender portal
The Microsoft 365 Security Center is the new home for monitoring & managing security across your Microsoft identities, data, devices, & apps. 

- Security health of the organization can be seen here. 
- New experience brings Defender for Endpoint, Defender for Office 365, and MCAS data into the Microsoft 365 security center. 
- https://security.microsoft.com

Secure Score

Reports & Dashboards

Incidents
- Incidents are a collection of correlated alerts created when a suspicious event is found. 
- Alerts are generated from different devices, users, and mailbox entities, and can come from many different domains. 
- Provides a comprehensive view & context of an attack. 

Incident Management 
- You can manage incidents on devices, user accounts, and mailboxes from the incident queue. 
