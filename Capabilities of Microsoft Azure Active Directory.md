# Describe the basic identity services and identity types of Azure AD
## Describe Azure AD
Azure AD is a cloud-based IAM solution that enables employees access to external resources, like M365, Azure Portal, and thousands of other SaaS solutions. Azure AD also helps employees access internal resources like apps within the corporate intranet, and any cloud apps developed for the org. 

## Describe Azure AD identities
Identity: A thing that can be authenticated. An identity can be a user with a username and password, or it can be an app or server that requires authentication through secret keys or certificates.

Azure AD manages different types of identities: 
- Users
- Service principals
- Managed identities
- Devices

### User
A user identity is a representation of something managed by Azure AD. Employees and guests are users in Azure AD. If there are multiple users that need the same access rights, you can create a group. Groups allow you to give access permissions to all members of the group instead of assigning them to individual users.

### Service principals
A service principal is an identity for an app. In order for an app to delegate its identity & access functions to Azure AD, the app must be registered with Azure AD before it's enabled for integration. After it's registered, a service principal can be created in each Azure AD tenant where the app is used. 

Service principals enable core features of Azure AD like authentication and authorization of apps to resources secured by Azure AD.

### Managed identity
Managed identities are a type of service principal that get automatically managed by Azure AD, which eliminates the need for devs to manage credentials. Managed identities provide an identity for apps to use when connecting to Azure resources that support Azure AD authentication & can be used without additional cost.

![Alt text](https://learn.microsoft.com/en-us/training/wwl-sci/explore-basic-services-identity-types/media/when-use-managed-identities-expanded.png#lightbox)

There are two types of managed identities:
- System-assigned
- User-assigned

### Devices

- Azure AD registered devices
- Azure AD joined
- Hybrid Azure AD joined devices



## Describe hybrid identity

## Describe the different external identity types

# Describe the authentication capabilities of Azure AD
## Describe the authentication methods available in Azure AD

## Describe Multi-factor Authentication

## Describe self-service password reset

## Describe password protection and management capabilities available in Azure AD

# Describe access management capabilities of Azure AD
## Describe conditional access

## Describe the benefits of Azure AD roles.

## Describe the benefits of Azure AD role-based access control

# Describe the identity protection and governance capabilities of Azure AD
## Describe identity governance in Azure AD

## Describe entitlement management and access reviews

## Describe the capabilities of Azure AD Privileged Identity Management (PIM)

## Describe Azure AD Identity Protection