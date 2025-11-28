---
description: Learn more about how Integration settings connect Adobe Learning Manager with third-party solutions
jcr-language: en_us
title: Integration settings in Adobe Learning Manager
---

# Integration settings in Adobe Learning Manager

## Login Methods

Adobe Learning Manager provides multiple login methods to ensure secure and flexible access for internal and external users. Administrators can configure these login methods based on organizational requirements.

The login methods available are:

* Adobe Learning Manager ID
* Adobe ID
* Single Sign-On

### Internal Users

The Internal Users section allows you to configure login options specifically for internal users. Internal users can access the account using either Adobe ID or Single Sign-On (SSO).

**Adobe ID:**

* Internal users can log in using their Adobe ID credentials.
* Suitable for organizations already using Adobe services.

**Single Sign-On (SSO):**

* Allows SSO for internal users to use the organization's identity provider (IdP).
* Supports SAML 2.0-based authentication for seamless login experiences.

To allow SSO logins fo rinternal users, select Enable Multiple Single Sign-On(SSO) for login and start configuring SSO.

The **[!UICONTROL SSO Active Field]** in Adobe Learning Manager is used to map Single Sign-On (SSO) configurations to specific user attributes or groups. You can configure this field to enable multiple SSO setups for internal users based on their organization, location, or other criteria.

### External Users

The External Users section in Adobe Learning Manager allows you to manage external learners, such as partners or agencies, who require limited access to the Adobe Learning Manager account. This section provides tools to create registration profiles, manage external user groups, and configure settings specific to external learners.

External users can log in using the following:

* Adobe ID: External users can log in using their Adobe ID credentials.
* Single Sign-On (SSO): External users can log in via SSO if configured by the administrator.
* Adobe Learning Manager ID: External users can create a Learning Manager username and password to access the platform.

**Key points:**

* You can enable one or more login methods for external users.
* If Adobe Learning Manager ID is selected, external users must create their own credentials.
* SSO can be configured for external users based on organizational needs.

### SSO configuration in Adobe Learning Manager

Adobe Learning Manager supports Single Sign-On (SSO) to allow users to authenticate once and gain access to multiple applications. Administrators can configure SSO for both internal and external users using SAML 2.0-based providers.

See [SSO logins in Adobe Learning Manager](/help/migrated/administrators/feature-summary/multiple-sso-logins.md) for more information.

>[!NOTE]
>
>* Up to 20 SSO configurations can be added to an account.
>* Contact Adobe support for assistance with SAML 2.0-based SSO providers.

## Data sources

Data sources allow you or integration administrators to integrate external systems for importing and syncing user and learning data. This feature ensures seamless data management and synchronization with systems like HRMS, Salesforce, FTP, and others.

**Examples of data source types**

* **FTP connectors**: FTP-based data sources allow organizations to upload user data files directly to Adobe Learning Manager through secure file transfer protocols. These connections are particularly useful for batch imports of user information, course enrollments, and other bulk data operations.
* **Third-party integrations**: Adobe Learning Manager supports integration with various enterprise systems through pre-built connectors. These integrations can include HR management systems, customer relationship management platforms, and other learning management systems.
*** Salesforce integration**: The Salesforce connector enables direct synchronization of user data, course information, and learning records between Salesforce and Adobe Learning Manager.

See [Connectors in Adobe Learning Manager](/help/migrated/integration-admin/feature-summary/connectors.md) for more information.

## Peer accounts

Peer accounts in Adobe Learning Manager allow you to share purchased seats and view reports across associated accounts. This feature is useful for organizations that need to collaborate or share resources between different accounts.

See [Peer accounts](/help/migrated/administrators/feature-summary/peer-account.md) in Adobe Learning Manager for more information.





