# Describe basic security capabilities in Azure
## Describe Azure DDoS protection

## Describe Azure Firewall

## Describe Web Application Firewall

## Describe Network Segmentation with Azure Virtual Networks

## Describe Azure Network Security groups

## Describe Azure Bastion and JIT Access

## Describe ways Azure encrypts data

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
