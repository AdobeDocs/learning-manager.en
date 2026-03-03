---
title: Adobe Learning Manager- secure administration guide
description: This guide outlines security settings, roles, and best practices for managing administrative security and access control in Adobe Learning Manager to ensure compliance and security.
jcr-language: en-us
exl-id: 67dd9334-9718-4b2a-841e-5d8bd5c42714
---
# Administrative security settings and security implications

## Administrative roles with security impact

Adobe Learning Manager uses a role-based access control (RBAC) model. The following table maps FedRAMP account tiers to the ALM roles referenced throughout this document:

| FedRAMP Term | ALM Role | Security Relevance |
|-------------|---------|------------------|
| Top-level administrative account | Administrator | Full account-level control. Exclusive access to all security-relevant settings described in this document. This is the role referred to throughout this guide when the term 'top-level administrative account' is used.  |
| Privileged account (scoped) | Custom Administrator | Delegated administrative access scoped to specific functions, user groups, or catalogs. Cannot access account-level security settings unless explicitly granted.  |
| Privileged account (integration) | Integration Administrator | Manages integrations, API registrations, and connector configurations. Elevated privileges scoped to integration management. Cannot modify other account-level security settings.  |

>[!NOTE]
>
>Only users explicitly assigned these roles can modify administrative or security-relevant settings. The settings documented in Sections 3–7 are accessible exclusively to the Administrator role unless otherwise stated.

## Login and authentication settings

Login and authentication settings control how all users — including administrators — access the ALM platform. These settings are configured exclusively by the Administrator role and have a direct and significant impact on the security posture of the entire account.

### Login method configuration

**Location:** ALM Admin > Settings > Login Methods 

The Administrator controls the authentication method used for all internal and external users. Options include: 

- **Adobe ID:** Users authenticate via their personal Adobe account. Managed by Adobe, not the organization.
- **Single Sign-On (SSO) via SAML 2.0:** Users authenticate via the organization's identity provider (IdP). The organization fully controls authentication, MFA, and session policy.
- **Learning Manager ID:** Available for external users only. Users create a platform-specific username and password.
- **Multiple SSO configurations:** Up to 20 SSO configurations can be added to support different user groups, locations, or organizational divisions

| Login Method | Security Implication | Recommendation |
|-------------|---------------------|----------------|
| **Adobe ID** | Organization has no control over password policy, MFA, or account recovery. A compromised personal Adobe account grants access to the ALM platform. | **NOT RECOMMENDED** for administrative or internal users. Use only when SSO is unavailable. |
| **SSO (SAML 2.0 / Federated ID)** | Authentication is fully controlled by the organization's IdP. MFA, session timeouts, and conditional access policies are enforced at the IdP level. Immediate revocation on user departure. | **RECOMMENDED** for all internal users and administrators. Provides the highest level of organizational control. |
| **Learning Manager ID** | Users self-manage passwords outside the organization's identity infrastructure. Cannot enforce MFA through ALM. Password strength depends on user behavior. | Acceptable for external users only. Not suitable for employees or administrators. |

>[!CAUTION]
>
>If the login method is set to Adobe ID for internal users, the organization loses the ability to enforce multi-factor authentication, control password complexity, or immediately revoke access when a user leaves. This significantly increases the risk of unauthorized access.

See [Custom roles](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role) for more information.

### Multi-Factor Authentication (MFA)

**Location:** Adobe Admin Console > Settings > Privacy and Security > Authentication Settings

MFA enforcement for **Adobe ID** and **Enterprise ID** users is configured by the **System Administrator** in the Adobe Admin Console, not within the ALM application itself.  For **Federated ID / SSO** users, MFA is enforced at the organization's identity provider.

- **Enforced 2FA:** Users cannot disable two-step verification. Provides strong protection against credential theft and phishing.
- **Optional 2FA:** Users choose whether to enable two-step verification. Significantly weaker security posture.
- **MFA not configured:** Passwords alone protect access. High risk, particularly for administrative accounts.

>[!IMPORTANT]
>
>Administrative accounts without enforced MFA are at significantly higher risk of unauthorized access. A compromised admin credential without MFA grants full account control, including the ability to modify all security settings.

### Session Life and Idle Timeout

**Location:** Adobe Admin Console > Settings > Privacy and Security > Advanced Settings

The **System Administrator** configures the maximum active session lifetime and the idle session timeout for the organization. These settings apply to all users, including administrators.

- **Max Session Life:** Forces re-authentication after a defined period regardless of activity. Limits the window of opportunity if a session is compromised.
- **Max Idle Time:** Terminates sessions that have been inactive for a defined period. Protects against unattended authenticated sessions on shared or unlocked devices.

## Role Assignment and Privilege Scope Settings

Role assignment and privilege scope settings determine who has administrative access in ALM and what they can do. These are among the highest-impact security settings in the platform. Only the Administrator role can create, assign, modify, or revoke administrative roles.

### Administrative Role Assignment

**Location:** ALM Admin > Users > Internal > Actions > Assign Role / Remove Role

The **Administrator** can grant or revoke the following roles:

- **Administrator:** Full account-level access
- **Author:** Content creation access
- **Custom Administrator:** Scoped administrative access (see Section 4.2)
- **Integration Administrator:** Integration and API access (see Section 7)

| Setting / Action | Security Implication | Recommended Practice |
|---|---|---|
| **Granting Administrator role** | Full account control. A user with this role can modify all settings in this document, including reconfiguring authentication and revoking other admins' access. | Assign only to a minimum number of users with a verified business need. Maintain a documented list of all Administrator-role holders. |
| **Failing to revoke roles on departure** | Departed users retain access to administrative functions. Risk of unauthorized access, data exfiltration, or sabotage. | Remove roles immediately when a user's employment or administrative responsibilities change. Conduct periodic access reviews. |
| **Over-assigning broad roles** | Broad administrative access increases the potential impact of a compromised account and reduces accountability for administrative actions. | Apply the principle of least privilege. Prefer scoped roles (for example, Custom Administrator) where possible. |

### Custom Administrative Role Configuraton

**Location:** ALM Admin > Users > Custom Roles > Create Role

Apply the principle of **least privilege**. Use **Custom Administrator** roles to delegate specific functions (see Section 4.2).

The **Administrator** can create custom roles that grant a defined subset of administrative permissions. Custom roles can be scoped to specific user groups, catalogs, or feature sets, limiting the reach of delegated administrative access.

**Available permission categories include:**

- **Account privileges:** Access to system-wide configurations such as announcements, gamification, skills, and user management.
- **Feature privileges (core):** Access to catalogs, reports, and tags.
- **Feature privileges (learning objects):** Access to courses, certifications, learning paths, and job aids.
- **Scope:** Restrict the role to specific user groups and/or catalogs.

| Configuration Decision | Security Implication | Recommended Practice |
|---|---|---|
| **Creating an overly broad custom role** | A custom role with excessive privileges provides little security benefit over the full Administrator role and increases the blast radius of a compromised account. | Scope custom roles to the minimum set of permissions needed for the specific function. Prefer catalog-scoped and user-group-scoped roles. |
| **Granting Settings access to a custom admin** | Custom admins with Settings access can modify login methods, notification settings, and other account-level configurations. | Only grant Settings access to custom roles when explicitly required. Audit which custom roles have this privilege regularly. |
| **Not auditing custom role assignments** | Undocumented or unreviewed custom roles may accumulate over time, leading to privilege creep. | Periodically download the Custom Role Report (**Users > Custom Roles > Download**) and review all active custom role assignments. |

## User Provisioning and Access Management Settings

User provisioning settings control how users are added to the platform, how long they remain active, and when their data is removed. These settings are configured exclusively by the Administrator role and have direct security implications for data exposure and access control. 

| Setting | Location | Security Implication | Recommended Default |
|---|---|---|---|
| **Inactive user auto-deletion** | ALM Admin > Settings > General | Without auto-deletion, inactive accounts accumulate. Dormant accounts are a common target for unauthorized access because they may go unmonitored. | Enable. Set a retention period aligned with organizational policy (for example, 90 days of inactivity). |
| **External user profile expiry** | ALM Admin > Users > External > Add Profile | External user profiles without an expiry date remain accessible indefinitely. Partners or contractors who no longer require access retain an active entry point. | Set an expiry date on every external user profile at creation time. |
| **Self-registration link controls** | ALM Admin > Users > Internal > Add > Self Registration | A self-registration link allows any user with the URL to create a learner account. If not managed, this can result in unauthorized or unexpected users gaining platform access. | Generate self-registration links only when needed. Disable or revoke unused links promptly. |
| **External profile pause / resume** | ALM Admin > Users > External > Actions > Pause | Pausing an external profile prevents new users from registering but does not affect those already registered. Failing to pause inactive external profiles may allow unintended registrations. | Pause external profiles when registration is no longer needed. Delete profiles that are permanently inactive. |
| **User deletion and purge** | ALM Admin > Users > Internal > Actions > Delete / User Cleanup > Purge | Deleted users are deactivated but their data is retained. Purging permanently removes all user data. Failure to purge departed users may retain sensitive learning records and PII beyond the required retention period. | Purge user records in line with organizational data retention and privacy policies. Purging is irreversible.|

>[!IMPORTANT]
>
>Purging is permanent and irreversible. All learning records, enrollment data, and user information are deleted. If a purged user is referenced in connector configurations, those connectors will be disabled. Confirm selection carefully before executing a purge.

## Reporting and Data Access Settings

Reporting and data access settings determine which users can view, generate, and export platform data. Misconfiguration of these settings can result in exposure of sensitive personal, organizational, or compliance-related information. 

| Setting | Location | Security Implication | Recommended Default |
|---|---|---|---|
| **Granting report access to custom roles** | ALM Admin > Users > Custom Roles > Feature Privileges > Reports | Reports may contain personally identifiable information (PII), course completion data, assessment scores, and learner progress. Access to reporting features should be limited to users with a verified business need. | Grant report access only to roles with a specific, documented need. Use read-only access where write access is not required. |
| **Full Control vs. Read Only report scope** | ALM Admin > Users > Custom Roles > Account Summary Report | Full Control on Account Summary Report grants the custom admin visibility across all user groups and catalogs, regardless of their role scope. This can expose data outside the intended scope of a scoped admin role. | Grant Full Control on Account Summary Report only to roles that genuinely require organization-wide reporting visibility. |
| **xAPI and email report access** | ALM Admin > Users > Custom Roles | xAPI reports and email reports are available only to the full Administrator role. These reports may contain detailed behavioral and communication data. Access is restricted by design. | Do not attempt to delegate xAPI or email report access through custom roles. These are Administrator-only by design. |
| **Exported user data** | ALM Admin > Users > Internal > Export User Data | The Export User Data function generates a downloadable file containing all internal user records. This data must be handled in accordance with organizational security and privacy policies. | Limit export capability to authorized personnel. Treat exported data as sensitive. Do not store or transmit it outside approved systems. |

## Integration and API Access Settings

Integration and API access settings control how external systems connect to Adobe Learning Manager. These settings extend access beyond the ALM user interface and, if misconfigured, can expose platform data and functionality to unauthorized systems.  Integration settings are managed by the Integration Administrator role. The full Administrator role retains the ability to review, approve, and revoke registered applications. 

| Setting | Location | Security Implication | Recommended Default |
|---|---|---|---|
| **API application registration** | Integration Admin > Applications > Register | Registering an application creates OAuth 2.0 credentials (Client ID and Secret) that can be used to access ALM data and functions programmatically. Overly broad OAuth scopes (for example, Admin role read/write) grant full administrative API access. | Grant the minimum required OAuth scopes. Review and revoke unused or legacy application registrations periodically. Treat client credentials as sensitive secrets. |
| **OAuth application scope** | Integration Admin > Applications > Register > Scopes | The available OAuth scopes range from learner read access to admin read/write access. Admin role read/write allows an application to modify any data an administrator can modify, including user roles and security settings. | Use the most restrictive OAuth scope that satisfies the integration's requirements. Never grant Admin role read/write access unless strictly necessary. |
| **Connector configuration (FTP, Salesforce, HRIS, etc.)** | Integration Admin > Connectors | Connectors enable automated import and export of user data, skills, and course completions. Misconfigured connectors can import incorrect user data, assign unintended roles, or export sensitive data to unauthorized destinations. | Review all active connector configurations periodically. Ensure data sources and destinations are authorized. Disable connectors that are no longer in use. |
| **Webhook configuration** | Integration Admin > Webhooks | Webhooks send real-time ALM event data (enrollments, completions, user changes) to a specified external URL. A misconfigured or compromised webhook endpoint can result in data exfiltration or exposure of sensitive learner events. | Register only verified, organization-approved webhook URLs. Review active webhook configurations regularly. Remove inactive or unrecognized webhooks immediately. |
| **LTI integration configuration** | Integration Admin > LTI Integrations | LTI integration allows ALM to act as an LTI provider or consumer, enabling external LMS platforms to access ALM courses. Once enabled, LTI cannot be disabled. Exposed LTI credentials can allow unauthorized access to course content. | Enable LTI only when a verified integration requirement exists. Treat LTI credentials as sensitive. Share credentials only with authorized LMS administrators. |

## Administrative Configuration Responsibilities and Shared Responsibility

Administrative settings in Adobe Learning Manager are configurable by customers and are part of the customer-managed security controls under Adobe's shared responsibility model. 

| Adobe Responsibilities | Customer Responsibilities |
|---|---|
| Secure operation of the ALM platform and underlying infrastructure. | Configuration of all administrative roles and permissions. |
| Enforcement of the role-based access control (RBAC) model. | Selecting and enforcing appropriate login methods and MFA. |

Additional information about Adobe Learning Manager's security practices is available in:

**Reference:** [Adobe Learning Manager Security Overview (PDF)](https://experienceleague.adobe.com/docs/learning-manager/assets/alm-security-whitepaper-2024.pdf)

## Document Maintenance

This document may be updated periodically to reflect changes in Adobe Learning Manager functionality or security guidance. The version and last-updated date are maintained in the document metadata and in the FedRAMP authorization package. Customers should refer to the publicly available version on Adobe Experience League to ensure they are using the most current guidance.
