---
title: Adobe Learning Manager Administrative Account Lifecycle
description: This document provides comprehensive guidance on securely managing top-level administrative accounts in Adobe Learning Manager (ALM) to meet FedRAMP compliance and best security practices.
jcr-language: en-us
exl-id: 79049f3d-8ebe-47e7-9895-9a7aaee504b3
---
# Administrative account types in Adobe Learning Manager 

## ALM role mapping

In Adobe Learning Manager, the top-level administrative account is the Administrator role. This is the role referred to whenever this guide uses the FedRAMP term 'top-level administrative account.' Custom Administrators and Integration Administrators are treated as privileged (scoped) accounts. 

The table below maps FedRAMP account tiers to the specific roles used in Adobe Learning Manager:

| FedRAMP Term                         | ALM Role Name              | Description |
|--------------------------------------|----------------------------|-------------|
| Top-level administrative account     | Administrator              | Highest-privilege role in ALM. Full control over users, roles, learning content, reporting, integrations, and all system configurations. Directly maps to the FedRAMP top-level administrative account definition.|
| Privileged account (scoped)          | Custom Administrator       | A defined subset of Administrator permissions scoped to specific functions (for example, reporting, catalog management). Does not have full account-level control.|
| Privileged account (integration)     | Integration Administrator  | Manages integrations and API-based access between ALM and external systems. Elevated privileges scoped to integration management only.|


Adobe Learning Manager uses a role-based access control (RBAC) model to manage administrative access. Administrative roles are assigned only by authorized administrators.

See [Custom roles in Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role) for more information

## Identity types and recommended authentication

Adobe Admin Console supports three identity types for admin accounts. The choice of identity type has direct security implications:

| Identity Type              | Description                                                                 | Security Recommendation                                                                 |
|---------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Adobe ID (Personal ID)    | Default type; managed by Adobe. Anyone can create one.                     | NOT RECOMMENDED for admins. The organization has no control over this account type.    |
| Enterprise ID             | Org-owned account managed by an Admin Console System Administrator.        | Acceptable if Federated ID/SSO is not available. Enforce 2FA.                          |
| Federated ID (SSO)        | Org-owned; integrated with SAML 2.0 SSO. Organization controls authentication entirely. | RECOMMENDED. Authenticates via org's IdP; supports MFA enforcement at the identity provider level. |

See the following for more information:

* [Identity types](https://helpx.adobe.com/enterprise/using/admin-console.html)
* [Secure user authentication and passwords](https://helpx.adobe.com/enterprise/using/authentication-settings.html)

## Role assignment and access control

Access to administrative accounts in Adobe Learning Manager is controlled through explicit [role assignment](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups) by an existing administrator. Key characteristics of secure administrative access include: 

* Administrative roles are assigned only by authorized administrators. 
* Access is role-based and scoped according to assigned permissions. 
* Organizations are responsible for limiting administrative access to users with a legitimate business need.

Adobe recommends that customers periodically review administrative access to ensure adherence to the principle of least privilege.

## Enforce Multi-Factor Authentication (MFA)

Adobe strongly recommends that administrators enforce two-step verification (2FA) organization-wide. MFA applies to Enterprise ID and Adobe ID users. Federated ID users should have MFA enforced at their organization's identity provider. 

To enforce 2FA in the Adobe Admin Console:

1. Sign in to the Adobe Admin Console.
2. Navigate to Settings > Privacy and Security > Authentication Settings. 
3. Enable Two-step verification and select the Enforce option to prevent users from disabling it. 
4. Optionally configure IP-based access restrictions and advanced session settings (Max Session Life / Max Idle Time).

>[!IMPORTANT]
>
>Adobe recommends enforcing 2FA and not leaving it optional for users. 2FA may take up to 24 hours to apply. For Federated ID users, enforce MFA at your identity provider.

See [Secure user authentication for more information](https://helpx.adobe.com/enterprise/using/authentication-settings.html) for more information.


## Sign in as administrator

ALM [Administrators](https://experienceleague.adobe.com/en/docs/learning-manager/using/get-started/getting-started-admin) sign in directly to the ALM platform using organizational credentials managed through the Admin Console. 

### Assign an administrator role

Within the ALM platform, administrators configure administrative access by creating and managing roles, assigning permissions to users, and defining permission scope based on operational responsibilities.

To assign the Administrator role in ALM:

1. Log in to Adobe Learning Manager as an existing Administrator. 
2. Navigate to Users > Internal. 
3. Search for or select the target user. 
4. Select Actions > Assign Role > Make Admin.

Custom administrative roles enable customers to delegate administrative tasks while maintaining centralized control over account-level privileges. Custom admins can be scoped to specific user groups or catalogs.

See [Add users and user groups](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups) for more information.

## Configure login methods and SSO

ALM Administrators control the login methods available to all users via Settings > Login Methods, a critical security-relevant configuration: 

* **Internal users**: Set login mode to Adobe ID or Single Sign-On (SSO). SSO via SAML 2.0 is strongly recommended. 
* **External users**: Set login mode to Adobe ID, SSO, or Learning Manager ID. Align the selected method with your organization's security policy.

Adobe recommends using Federated ID / SAML 2.0 SSO as the login method for all internal users. This ensures authentication is fully controlled by your organization's identity provider, enabling centralized MFA enforcement and immediate account revocation upon user departure.

See [Settings](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/settings) for more information.

## Recommended secure defaults on provisioning

When an ALM account is first provisioned, Adobe recommends verifying the following default settings before granting any administrative user operational access:

| Setting                      | Recommended Secure Default                                      | Where to Configure                              |
|------------------------------|------------------------------------------------------------------|-------------------------------------------------|
| Login method — internal users | Single Sign-On (SSO) / Federated ID                              | ALM > Settings > Login Methods                  |
| Two-step verification (2FA)  | Enforced (not optional for any user)                             | Admin Console > Settings > Privacy and Security |
| Max session life             | 8 hours or per organization policy                               | Admin Console > Settings > Advanced Settings    |
| Max idle time                | 30 minutes or per organization policy                            | Admin Console > Settings > Advanced Settings    |
| Admin role scope             | Least-privilege; use Custom Admin roles where possible           | ALM > Users > Custom Roles                      |
| External user expiry         | Set an expiry date on every external user profile                | ALM > Users > External                          |

### Initial setup checklist for New Administrators 

When provisioning a new top-level admin account, complete the following before granting operational access:

* Confirm identity type is Enterprise ID or Federated ID — not Personal Adobe ID.
* Enforce 2FA at the Admin Console level (Settings > Authentication Settings).
* Configure SSO / Federated ID if not already enabled.
* Set Max Session Life and Max Idle Time in Admin Console > Settings > Advanced Settings.
* Limit admin role scope — assign only the permissions necessary for the user's responsibilities.
* Verify the admin account is tied to an organizational email address controlled by your IT team.
* Document the account in your organization's privileged access register.

## Operation of administrative accounts

### Day-to-aay administrative tasks

Administrative accounts are used to perform day-to-day operational tasks, including:

* **User lifecycle management**: Creating users, updating profiles, and making role changes.
* **Learning content management**: Managing courses, learning programs, certifications, and catalogs.
* **Reporting and analytics**: Generating and reviewing reports on learner progress and platform usage.
* **Integrations and system configuration**: Managing connectors, API-based access, and system-level settings.

Administrators are expected to follow their organization's internal access control and change management policies when performing administrative actions.

See [Frequently Asked Questions for Adobe Learning Manager Administrators](https://experienceleague.adobe.com/en/docs/learning-manager/using/faq/frequently-asked-questions-for-administrators)


### Role hierarchy and delegation

Adobe Admin Console uses a hierarchical admin structure. System Administrators can delegate responsibilities to lower-privilege roles to reduce the attack surface of the top-level admin account:

* Product Admin: Manages access to specific Adobe products (e.g., Adobe Learning Manager).
* Product Profile Admin: Manages user membership in specific product profiles.
* User Group Admin: Manages user group membership.
* ALM Custom Admin: Scoped administrator within ALM with configurable permissions per catalog and user group.

### Ongoing governance practices

The following practices should be followed by organizations operating ALM admin accounts on an ongoing basis:

* **Periodic access review**: Regularly audit the list of System Admins in Admin Console (Users > Administrators) and ALM Admins (Users > Internal) to ensure only current, authorized staff hold these roles.
* **Audit log monitoring**: The Admin Console Audit Log records all changes made by administrators. System Admins have full visibility. Review the log regularly for unauthorized changes.
* **Minimum standing access**: Avoid using top-level admin accounts for routine tasks. Reserve full admin access for tasks that specifically require it.
* **Session security**: Configure Max Session Life and Max Idle Time in Admin Console > Settings > Advanced Settings to limit exposure from unattended sessions.

See [Admin console overview](https://helpx.adobe.com/enterprise/using/admin-console.html) for more information.

### Manage user accounts under Admin control

ALM Administrators manage internal and external user accounts. Security-relevant operations include:
 
* User auto-deletion: In Settings, Administrators can configure inactive internal users to be automatically deleted after a specified number of days, reducing dormant account risk.
* External user expiry: Administrators set an expiry date when creating external user profiles. Expired accounts are automatically moved to an inactive state.
* User deletion: Administrators can manually delete users via Users > Internal > Actions > Delete User.
* User purging: After deletion, administrators can permanently purge user records to comply with data retention policies and prevent unauthorized access to stale user data.

See the following for more information:

* [Add user and user groups](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups)
* [Purge users](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/purge-users)

## Decomissioning of administrative accounts

Administrative access must be removed when it is no longer required. Decommissioning administrative accounts may include:

* Revoking administrative roles from users.
* Reducing privileges when full administrative access is no longer necessary.
* Removing users from the system when appropriate.

Regular review and removal of unnecessary administrative access helps maintain least-privileged access.

### Removing System Administrator Rights (Admin Console)

When a System Administrator leaves the organization or changes roles, privileges must be revoked promptly:

1. Sign in to the Adobe Admin Console as a System Administrator.
2. Navigate to Users > Administrators.
3. Select the administrator to remove.
4. Click the More Options (…) icon > Edit Admin, then remove the System Admin role — OR select Remove User to remove the user entirely from the organization.
5. If the admin held other roles (Product Admin, Support Admin, etc.), revoke those as well.

>[!IMPORTANT]
>
>If the departing administrator is the Contract Owner for the organization, the Contract Owner role must be transferred to another person before they can be removed. Contact Adobe support if needed.

See the following for more information:

* [Create, update, or remove user accounts on the Admin Console](https://helpx.adobe.com/enterprise/using/manage-users-individually.html)
* [How to leave your organization-owned account](https://helpx.adobe.com/enterprise/using/leave-organization.html)

### Remove the ALM administrator role

To revoke ALM Administrator access without deleting the user's account (e.g., when the person remains a learner):

1. Log in to Adobe Learning Manager as an Administrator.
2. Navigate to Users > Internal.
3. Search for and select the user.
4. Select Actions > Remove Role > Remove Admin.

The user reverts to the Learner role. Their learning history and course enrollments are preserved.

See [Add user and user groups](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups) for more information.

### Delete and purge users

When a user departs the organization entirely and their account should be removed from the platform:

* Delete the user: Users > Internal > select user > Actions > Delete User. This disables the account and removes active access.
* Purge the user: After deletion, go to Users > User Cleanup, select the deletion month, select the user, and choose Actions > Purge User. Purging permanently removes all user records.

See [Purge users](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/purge-users) for more information.


## Security and shared responsibility

Adobe Learning Manager operates under a shared responsibility model:

* Adobe is responsible for securing the underlying ALM platform and infrastructure.
* Customers are responsible for managing administrative access, role assignments, and user lifecycle activities within their ALM account.

Additional information about Adobe Learning Manager security practices is available in [ Adobe Learning Manager Security Overview (PDF)](https://experienceleague.adobe.com/docs/learning-manager/assets/alm-security-whitepaper-2024.pdf)

## Document maintenance

This document may be updated periodically to reflect changes in Adobe Learning Manager functionality or administrative best practices. The version and last-updated date are maintained in the document metadata and in the FedRAMP authorization package. Customers should refer to the publicly available version on Adobe Experience League to ensure they are using the most current guidance.

## Enhanced security capability coverage

### SCG-ENH-CMP

Adobe maintains documented component inventory, ownership, and lifecycle management processes to ensure controlled configuration and compliance across system components.

### SCG-ENH-API

Adobe enforces standardized API security controls, including authentication, authorization, and monitoring, supported by documented governance and platform safeguards.

### SCG-ENH-MRG

Adobe applies formal change and merge management processes, including review and approval controls, to maintain system integrity and reduce deployment risk.

### SCG-ENH-VRH

Adobe follows a defined vulnerability management and remediation process covering identification, prioritization, tracking, and timely resolution.
