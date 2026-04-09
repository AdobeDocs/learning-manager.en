---
title: Adobe Learning Manager- security settings and configuration management
description: This document outlines Adobe Learning Manager's administrative account types, security-related settings, recommended secure defaults, API capabilities, export functionality, configuration comparison methods, publication practices, and version history. It provides detailed guidance on how privileged accounts operate, their security implications, and how configuration management is supported across the platform.
jcr-language: en-us
exl-id: a2e34104-c417-407f-af85-9f3f4b2a9fcb
---
# Security settings and configuration management

This guide provides detailed responses to FedRAMP recommendations (FRR-RSC-03 to FRR-RSC-08) for Adobe Learning Manager (ALM). It outlines security best practices, recommended secure defaults, and tools for auditing, exporting, and managing privileged account settings. The document is designed for administrators and compliance teams to ensure secure configuration and management of ALM accounts. 

It also highlights areas where ALM meets or partially meets FedRAMP standards, with references to supporting documentation and resources available on Adobe Experience League.

+++What security-relevant settings can only be operated by Custom Administrators or Integration Administrators in Adobe Learning Manager, and what are their security implications?

Adobe Learning Manager's two privileged account types- Custom Administrator and Integration Administrator. Each has a defined set of security-relevant settings with documented implications.

**Custom Administrator — what they can operate**:

* Custom roles are configured by the full Administrator at ALM Admin > Users > Custom Roles. A custom admin can be granted access to one or more of these permission categories: Account Privileges (announcements, gamification, skills, user management), Feature Privileges (catalogs, reports, tags), and Learning Object Privileges (courses, certifications, learning paths).
* Scope is the most security-sensitive setting: a custom role can be restricted to specific user groups and/or specific catalogs. Without scope restriction, a custom role effectively has platform-wide access to its granted features — approaching the footprint of a full Administrator.
* If a custom role is granted Settings access under Account Privileges, that custom admin can modify login methods, notification settings, and account-level configurations — a high-impact privilege that should only be granted with explicit business justification.

**Integration Administrator — what they can operate**:

* Integration Administrators manage OAuth 2.0 application registrations at Integration Admin > Applications > Register. They select one of six OAuth scopes, ranging from Learner read access to Admin role read/write access. Admin read/write scope grants the registered application the same privileges as a full administrator via the API.
* Integration Administrators configure FTP, SFTP, Salesforce, Workday, and other connectors that import user records, role assignments, and course completions — and export platform data to external systems.
* Integration Administrators configure webhooks that push real-time ALM event data (enrollments, completions, role changes) to external URLs. A compromised or misconfigured webhook endpoint is a data exfiltration risk.
* Integration Administrators can configure LTI integrations. Once enabled, LTI cannot be disabled. 

**References**:

* [Custom roles | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)
* [Manage custom roles via CSV | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/configure-role-csv-files)
* [Application developer manual \| Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)
* [Adobe Learning Manager Connectors](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/connectors)

+++

+++What are the recommended secure defaults for top-level administrative and privileged accounts in Adobe Learning Manager, and where are they configured?

Adobe Learning Manager documents specific recommended secure defaults for both the Administrator role and privileged account types. 

* **Top-level Administrator account defaults (configured at first provisioning)**:

* Login method for internal users: Single Sign-On (SSO) via SAML 2.0: configured at ALM Admin > Settings > Login Methods. Do not use Adobe ID for employees or administrators.
* Two-step verification (2FA): Enforced for all users: configured at Adobe Admin Console > Settings > Privacy and Security > Authentication Settings.
* Max Session Life: 8 hours (or per org policy): configured at Adobe Admin Console > Settings > Privacy and Security > Advanced Settings.
* Max Idle Time: 30 minutes (or per org policy): same location as above.
* Inactive user auto-deletion: Enabled with an org-defined retention period (e.g., 90 days of inactivity): ALM Admin > Settings > General.
* External user profile expiry: Set on every external profile at creation: ALM Admin > Users > External. No indefinite external profiles.
* IP access restrictions: Restrict to approved IP ranges where feasible: Admin Console > Settings > Advanced Settings.

**Custom Administrator role defaults (configured when creating each role)**:

* OAuth scope for registered applications: minimum required scope. Never grant Admin role read/write access unless strictly necessary.
* Custom role scope: restrict to specific user groups and specific catalogs. Do not create custom roles with All Users and All Catalogs scope unless the function genuinely requires it.
* Settings access in custom roles: do not grant unless the specific function requires it, given the privilege escalation risk.

**Integration Administrator defaults**:

* API OAuth scope: select the most restrictive scope that satisfies the integration's requirements. Do not grant Admin read/write to applications that only need Learner read access.
* Connector credentials, LTI credentials, and webhook URLs: treat as sensitive secrets — never share via email or commit to source control.

**References**:

* [Settings | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)
* [Secure user authentication and passwords | Adobe Admin Console](https://helpx.adobe.com/enterprise/using/authentication-settings.html)
* [Custom roles | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)

+++

+++Does Adobe Learning Manager offer a way for administrators to compare current account settings against the recommended secure defaults?

Adobe Learning Manager does not have a dedicated comparison dashboard that automatically shows current settings alongside recommended secure defaults. 

**Custom Role Report: current privileged role assignments**:

* In ALM, navigate to Admin > Users > Custom Roles and click Download (top right) to export a CSV of all custom roles, their permission sets, and their scope assignments.
* Compare this export against the recommended defaults in FRR-RSC-02 Section 8 — specifically checking whether any custom role has Settings access, All Users scope, or All Catalogs scope without documented justification.

**ALM REST API: programmatic configuration retrieval**:

* The GET /account endpoint returns account-level configuration data in JSON format, accessible using Admin role OAuth scope. Customers can call this endpoint programmatically and diff the response against a baseline derived from the recommended defaults in FRR-RSC-02 Section 8.
* The GET /users endpoint (with include=role filter) returns current role assignments for all users, enabling automated detection of unexpected role assignments. 

>[!NOTE]
>
>Adobe Learning Manager does not offer a native side-by-side comparison UI. Customers requiring automated configuration compliance checking should integrate the ALM REST API with their existing tooling. 

**Reference**

* [Application developer manual | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)

+++

+++Can administrators export current security-relevant settings and configurations from Adobe Learning Manager in a machine-readable format?

Adobe Learning Manager supports export of security-relevant configuration data through several mechanisms. No single export produces a complete snapshot of all security settings at once, but the following exports collectively cover the full scope of security-relevant data. 

**ALM REST API: JSON export of current role assignments and account configuration**:

* GET /account: returns account-level settings in JSON, including active login configuration data and account metadata.
* GET /users?include=role: returns all users with their currently assigned roles in JSON.
* GET /userGroups — returns all user groups and their membership, relevant for auditing custom role scope.
* All API responses are JSON (vnd.api+json). Authentication uses OAuth 2.0 with Admin role read/write scope.

**Custom Role CSV export: current privileged role definitions**:

* ALM Admin > Users > Custom Roles > Download exports a CSV of all custom role definitions, their permission categories, and scope assignments.
* This export can be used as a machine-readable snapshot of current privileged account configuration.
**

**Jobs API: bulk user and role data**:

* The ALM Jobs API supports on-demand generation of user reports (including role assignments) in CSV format. These can be scheduled and consumed by external compliance or SIEM tools.

**Reference**

* [Application developer manual | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)

+++

+++Does Adobe Learning Manager provide an API through which security-relevant settings can be viewed and adjusted programmatically?

Adobe Learning Manager provides a full REST API v2 that allows programmatic viewing and adjustment of security-relevant settings using OAuth 2.0 authentication. The following are the specific API capabilities relevant to security settings:

**Authentication and scope**:

* Applications are registered by the Integration Administrator at Integration Admin > Applications > Register. OAuth 2.0 Client ID and Secret are issued per application.
* Six scopes are available. For security settings management, Admin role read/write access is required. This grants the application the same access as a full Administrator via the API.
* Access tokens are obtained via the standard OAuth authorization code or client credentials flow. Base URL: https://learningmanager.adobe.com/primeapi/v2/

**User and role management via API**:

* GET /users: retrieve all users and their current roles
* POST /users: programmatically provision new users
* PATCH /users/{id}: update user attributes including role assignments
* DELETE /users/{id}: disable a user account
* POST /users/{id}/purge: permanently purge a user and all associated records

Account configuration retrieval:

* GET /account: returns account-level configuration including account settings data in JSON format, including fields such as complianceLabelDefaultID, showComplianceLabel, and custom_injections.

+++

+++Does Adobe Learning Manager publish its secure configuration guidance in a machine-readable format such as OSCAL, JSON, or YAML?

Adobe Learning Manager does not currently publish its Secure Configuration Guide in a machine-readable format. The guidance in [FRR-RSC-01](/help/migrated/alm-administrative-lifecycle.md) and [FRR-RSC-02](/help/migrated/alm-secure-administration-guide.md) is published as human-readable documentation on Adobe Experience League in HTML and downloadable document formats.

There is no publicly available OSCAL component definition, YAML baseline, or JSON policy file encoding the recommended secure defaults for Adobe Learning Manager.

Customers needing automated comparison of current settings against recommended baselines should use the [ALM REST API](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual) to retrieve current configuration data in JSON format.

+++

+++Is Adobe Learning Manager's Secure Configuration Guide publicly available without requiring a login or special access?

**What is publicly available**:

* [FRR-RSC-01: Secure Administration Guide](/help/migrated/alm-administrative-lifecycle.md): full lifecycle guidance for top-level administrative accounts.
* [FRR-RSC-02: Administrative Security Settings and Implications](/help/migrated/alm-secure-administration-guide.md): all security-relevant settings, their implications, and recommended defaults.
* FRR-RSC-03–10 (this document) — Q&A responses to all eight FedRAMP SHOULD recommendations.

+++

+++Does Adobe Learning Manager provide versioning and a release history that allows agencies to track changes to security-relevant settings and recommended defaults over time?

Adobe Learning Manager maintains a publicly available, detailed release history for every product update. Security-relevant changes to administrative settings, authentication capabilities, API endpoints, and role management features are documented in each release.

**ALM Release Notes: numbered, cumulative change history**:

* Adobe publishes numbered release notes for every Adobe Learning Manager update (e.g., Update 100, Update 99). These are published on Experience League and document all new features, changes to existing settings, API additions and removals, connector changes, and deprecated capabilities.
* Each release note includes a dedicated section for API changes, listing new endpoints, modified response fields, and deprecations, directly relevant to security-relevant configuration capabilities.

**What's New pages: per-release feature summaries**:

* Each major release has a dedicated 'What's New' page documenting new security-relevant features with context. For example, the release notes include changes to custom role permission handling, the addition of CSV-created permissions visibility for custom roles, and API rate limiting changes.

**API Deprecations List: authoritative record of removed API capabilitie**s:

* Adobe maintains a dedicated API Deprecations page listing all deprecated and removed ALM API endpoints with the release version in which each deprecation occurred.

**References**:

* [Adobe Learning Manager Release Notes](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/release-notes)
* [What's New in Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/whats-new-july-2024)
* [API Deprecations in Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/api-deprecations-list)

+++
