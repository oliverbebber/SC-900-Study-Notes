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
Azure AD identity governance gives orgs the ability to:
- Govern the identity lifecycle
- Govern access lifecycle
- Secure privileged access for administration

It's intended to help orgs answer the following questions:
- Which users should have access to which resources?
- What are those users doing with that access?
- Are there effective organizational controls for managing access?
- Can auditor verify that the controls are working?

## Describe identity governance in Azure AD

## Describe entitlement management and access reviews
Entitlement management is an identity governance feature that enables orgs to manage the identity & access lifecycle at scale. It can automate the following:

- Access request workflows
- Access assignments
- Reviews
- Expiration

Azure AD Access Reviews enable orgs to manage:

- Group memberships
- Access to enterprise applications
- Role assignment

Regular access reviews ensure only the right people have access to resources they need. Excessive access rights are a security risk, but when people transfer departments, move between teams or take on additional responsibilities, access rights can become difficult to manage.

Access reviews are helpful when

- You have too many users in privileged roles, like global admin
- When automation isn't possible, like when HR data isn't in Azure AD
- You want to control business critical data access
- Governance policies require periodic review of access permissions

Access reviews can be create in Azure AD access reviews, or with Azure AD Privileged Access Management (PIM). They can be used to review & manage access for both users and guests.

When an access review is created, it can be set up to allow each user to review their own access OR to have one, or more, users review all users access. Guests can be asked to review their own access as well, or have their access reviewed by one or more users.

IMPORTANT: Access rights are NOT changed until the review is completed. 

When the review is complete, it can be set to automatically apply changes OR require manual changes to remove access from a group membership or application assignment, except for a dynamic group or groups that originates on-premises. In these cases, the changes must be applied directly to the group.

## Describe the capabilities of Azure AD Privileged Identity Management (PIM)
This is a service that enables orgs to manage, control, and monitor access to resources within the org.
- Azure AD
- Azure
- Other Microsoft online services like M365 & Intune

PIM mitigates the risks of excessive, unnecessary, or misused access permissions and requires justification to understand why users need permissions & enforces MFA to activate any role.

- Just in time, providing privileged access only when needed.
- Time-bound, assigning start and end dates that indicate when a user can access resources.
- Approval-based, requiring specific approval to activate privileges.
- Visible, sending notifications when privileged roles are enabled.
- Auditable, allowing a full access history to be downloaded for audits.

PIM can reduce the chance of a malicious actor getting access by minimizing the number of users who have access to secure information and resources. Time-limiting authorized users helps reduce the risk of an authorized user inadvertently affecting sensitive resources.

PIM can also provide insight about what users are doing with their admin privileges.

## Describe Azure AD Identity Protection
