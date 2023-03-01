# Describe security and compliance concepts
## Describe the shared responsibility model
Cloud security is a shared responsibility. This model defines the duties of customers and cloud service providers (CSPs) in ensuring the cloud environment is secure.

![Alt text](https://learn.microsoft.com/en-us/azure/security/fundamentals/media/shared-responsibility/shared-responsibility.svg)

In **all** cloud deployment types, you own the data and identities.
- You are responsible for protecting the security of any data, identities, and on-prem resources.
- You are also responsible for the cloud components you control, which will vary depending on the service type. 

The following responsibilities are **always** the customer's responsibility:
- Data
- Endpoints/devices
- Accounts
- Access management


![Alt text](https://learn.microsoft.com/en-us/azure/security/fundamentals/media/shared-responsibility/cloud-enabled-security.svg)




## Describe defense in depth
A layered (defense in depth) approach that doesn't rely on one method to completely protect your environment.

This approach includes implementing security controls at various layers of the technology stack, such as

Physical security:
- Video surveillance
- Access controls
- Alarms

Network security:
- Firewalls
- IDS/IPS

Host security:
- Antivirus
- IDS/IPS
- Other endpoint protection technologies

Application security:
- Secure coding practices
- Performing code reviews
- Using application security testing tools

Data security:
- Encryption
- Access controls
- DLP technologies


## Describe the Zero-Trust model
Zero Trust is a security strategy.

- Verify explicitly: Always authenticate & authorize based on all available data points.
- Use least privilege: Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection.
- Assume breach: Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses.

With ZT, we move away from trust-by-default to trust-by-exception. 




## Describe encryption and hashing

## Describe compliance concepts

# Define identity concepts
## Define identity as the primary security perimeter

## Define authentication

## Define authorization

## Describe identity providers

## Describe Active Directory

## Describe the concept of Federation

