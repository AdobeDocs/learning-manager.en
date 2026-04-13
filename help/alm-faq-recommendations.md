---
title: Adobe Learning Manager Administrative Account Lifecycle
description: This document provides a comprehensive summary of Adobe Learning Manager's (ALM) security account management, configuration, and compliance features aligned with FedRAMP recommendations.
jcr-language: en-us
---

# Adobe Learning Manager security recommendations

## What security-relevant settings can only be operated by Custom Administrators or Integration Administrators in Adobe Learning Manager, and what are their security implications?

Adobe Learning Manager's two privileged account types — Custom Administrator and Integration Administrator — each have a defined set of security-relevant settings with documented implications.

### Custom Administrator: what they can operate:

* Custom roles are configured by the full Administrator at ALM Admin > Users > Custom Roles. A custom admin can be granted access to one or more of these permission categories: Account Privileges (announcements, gamification, skills, user management), Feature Privileges (catalogs, reports, tags), and Learning Object Privileges (courses, certifications, learning paths).
* Scope is the most security-sensitive setting: a custom role can be restricted to specific user groups and/or specific catalogs. Without scope restriction, a custom role effectively has platform-wide access to its granted features — approaching the footprint of a full Administrator.
* If a custom role is granted Settings access under Account Privileges, that custom admin can modify login methods, notification settings, and account-level configurations — a high-impact privilege that should only be granted with explicit business justification.
* A custom admin with Settings access who also has Users entity access can assign the full Administrator role to themselves, effectively escalating to full administrative control.

### Integration Administrator: what they can operate:

* Integration Administrators manage OAuth 2.0 application registrations at Integration Admin > Applications > Register. They select one of six OAuth scopes, ranging from Learner read access to Admin role read/write access. Admin read/write scope grants the registered application the same privileges as a full administrator via the API.
* Integration Administrators configure FTP, SFTP, Salesforce, Workday, and other connectors that import user records, role assignments, and course completions, and export platform data to external systems.
* OAuth scope for registered applications: minimum required scope. Never grant Admin role read/write access unless strictly necessary.
* Integration Administrators configure webhooks that push real-time ALM event data (enrollments, completions, role changes) to external URLs. A compromised or misconfigured webhook endpoint is a data exfiltration risk. 
* Integration Administrators can configure LTI integrations. Once enabled, LTI cannot be disabled. Exposed LTI credentials allow unauthorized access to course content from external LMS platforms. 


## What are the recommended secure defaults for top-level administrative and privileged accounts in Adobe Learning Manager, and where are they configured? 

### Top-level Administrator account defaults (configured at first provisioning):

* Login method for internal users: Single Sign-On (SSO) via SAML 2.0: configured at ALM Admin > Settings > Login Methods. Do not use Adobe ID for employees or administrators.
* Two-step verification (2FA): Enforced for all users: configured at Adobe Admin Console > Settings > Privacy and Security > Authentication Settings.
* Max Session Life: 8 hours (or per org policy): configured at Adobe Admin Console > Settings > Privacy and Security > Advanced Settings.
* Max Idle Time: 30 minutes (or per org policy): same location as above.
* Inactive user auto-deletion: Enabled with an org-defined retention period (e.g., 90 days of inactivity): ALM Admin > Settings > General.
* External user profile expiry: Set on every external profile at creation- ALM Admin > Users > External. No indefinite external profiles.
* IP access restrictions: Restrict to approved IP ranges where feasible- Admin Console > Settings > Advanced Settings.

### Custom Administrator role defaults (configured when creating each role):

* OAuth scope for registered applications: minimum required scope. Never grant Admin role read/write access unless strictly necessary. 
* Custom role scope: restrict to specific user groups and specific catalogs. Do not create custom roles with All Users and All Catalogs scope unless the function genuinely requires it. 
* Settings access in custom roles: do not grant unless the specific function requires it, given the privilege escalation risk. 

### Integration Administrator defaults:

* API OAuth scope: select the most restrictive scope that satisfies the integration's requirements. Do not grant Admin read/write to applications that only need Learner read access.
* Connector credentials, LTI credentials, and webhook URLs: treat as sensitive secrets — never share via email or commit to source control.

## Does Adobe Learning Manager offer a way for administrators to compare current account settings against the recommended secure defaults?

Adobe Learning Manager does not have a dedicated comparison dashboard that automatically shows current settings alongside recommended secure defaults. However, three platform capabilities allow administrators to audit and compare current configurations manually or programmatically. 

### Custom Role Report- current privileged role assignments: 

In ALM, navigate to Admin > Users > Custom Roles and click Download (top right) to export a CSV of all custom roles, their permission sets, and their scope assignments. 

### ALM REST API- programmatic configuration retrieval: 

* The GET /account endpoint returns account-level configuration data in JSON format, accessible using Admin role OAuth scope. Customers can call this endpoint programmatically. 
* The GET /users endpoint (with include=role filter) returns current role assignments for all users, enabling automated detection of unexpected role assignments. Use the Jobs API for bulk user exports.

## Can administrators export current security-relevant settings and configurations from Adobe Learning Manager in a machine-readable format? 

Adobe Learning Manager supports export of security-relevant configuration data through several mechanisms. No single export produces a complete snapshot of all security settings at once, but the following exports collectively cover the full scope of security-relevant data.

### Admin Console Audit Log — CSV export of all authentication and role changes:

* In the Adobe Admin Console, navigate to **Insights > Logs > Audit Log**, apply filters as needed, and click **Export CSV**
* The exported CSV records every administrative action including: 2FA enforcement changes, session limit changes, admin role assignments and removals, user deletions, and product entitlement changes — all with timestamps and actor identity.
* Data is retained for 90 days. Global Admin Console users can export logs across all organizations.

### ALM REST API — JSON export of current role assignments and account configuration:

* `GET /account` — returns account-level settings in JSON, including active login configuration data and account metadata.
* `GET /users?include=role` — returns all users with their currently assigned roles in JSON.
* `GET /userGroups` — returns all user groups and their membership, relevant for auditing custom role scope.
* All API responses are JSON (`vnd.api+json`). Authentication uses OAuth 2.0 with Admin role read/write scope.

### Custom Role CSV export — current privileged role definitions:

* ALM Admin > Users > Custom Roles > Download exports a CSV of all custom role definitions, their permission categories, and scope assignments.
* This export can be used as a machine-readable snapshot of current privileged account configuration.

### Jobs API — bulk user and role data:

* The ALM Jobs API supports on-demand generation of user reports (including role assignments) in CSV format. These can be scheduled and consumed by external compliance or SIEM tools.

See [Adobe Learning Manager- Application developer manual](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual) for more information.

## Does Adobe Learning Manager provide an API through which security-relevant settings can be viewed and adjusted programmatically? 

Adobe Learning Manager provides a full REST API v2 that allows programmatic viewing and adjustment of security-relevant settings using OAuth 2.0 authentication. The following are the specific API capabilities relevant to security settings:

### Authentication and Scope

* Applications are registered by the Integration Administrator at **Integration Admin > Applications > Register**. OAuth 2.0 Client ID and Secret are issued per application.
* Six scopes are available. For security settings management, **Admin role read/write** access is required. This grants the application the same access as a full Administrator via the API.
* Access tokens are obtained via the standard OAuth authorization code or client credentials flow.  
  **Base URL:**  
  `https://learningmanager.adobe.com/primeapi/v2/`

### User and Role Management via API

* `GET /users` — retrieve all users and their current roles
* `POST /users` — programmatically provision new users
* `PATCH /users/{id}` — update user attributes including role assignments
* `DELETE /users/{id}` — disable a user account
* `POST /users/{id}/purge` — permanently purge a user and all associated records

### Account Configuration Retrieval

* `GET /account` — returns account-level configuration including account settings data in JSON format, including fields such as:
  * `complianceLabelDefaultID`
  * `showComplianceLabel`
  * `custom_injections`

### Adobe User Management API (Admin Console Layer)

* The Adobe User Management API (UMAPI) provides programmatic access to Admin Console operations:
  * User provisioning
  * Product entitlement assignment
  * System Administrator role assignment at the organization level
* UMAPI is separate from the ALM REST API and operates at the Adobe organization level. Use it for automating Admin Console role assignments and user provisioning.

## Does Adobe Learning Manager publish its secure configuration guidance — the recommended defaults — in a machine-readable format such as OSCAL, JSON, or YAML? 

Adobe Learning Manager does not currently publish its Secure Configuration Guide in a machine-readable format.

## Is Adobe Learning Manager's Secure Configuration Guide publicly available without requiring a login or special access? 

Yes. Adobe Learning Manager's Secure Configuration Guide is publicly available on Adobe Experience League. No account, login, or license is required to access it. 

What is publicly available:

* FRR-RSC-01: Secure Administration Guide: full lifecycle guidance for toplevel administrative accounts.
* FRR-RSC-02: Administrative Security Settings and Implications — all securityrelevant settings, their implications, and recommended defaults.

## Does Adobe Learning Manager provide versioning and a release history that allows agencies to track changes to security-relevant settings and recommended defaults over time?

Adobe Learning Manager maintains a publicly available, detailed release history for every product update. Security-relevant changes to administrative settings, authentication capabilities, API endpoints, and role management features are documented in each release.

### ALM Release Notes — Numbered, Cumulative Change History

* Adobe publishes numbered release notes for every Adobe Learning Manager update (e.g., *Update 100*, *Update 99*).
* These are published on **Experience League** and document:
  * New features
  * Changes to existing settings
  * API additions and removals
  * Connector changes
  * Deprecated capabilities
* Each release note includes a dedicated section for **API changes**, listing:
  * New endpoints
  * Modified response fields
  * Deprecations  
  * These are directly relevant to security-relevant configuration capabilities.

### "What's New" Pages — Per-Release Feature Summaries

* Each major release has a dedicated **"What's New"** page documenting new security-relevant features with context.
* Examples of documented security-related updates include:
  * Changes to custom role permission handling
  * Addition of CSV-created permissions visibility for custom roles
  * API rate limiting changes

### API Deprecations List — Authoritative Record of Removed API Capabilities

* Adobe maintains a dedicated **API Deprecations** page listing all deprecated and removed ALM API endpoints, including the release version in which each deprecation occurred.
* Examples of security-relevant deprecations include:
  * Changes to the `GET /users` endpoint's sort and override behavior
  * Notification, report date filter requirements

