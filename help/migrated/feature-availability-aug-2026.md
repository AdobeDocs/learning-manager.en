---
description: Learn which app surfaces support new Adobe Learning Manager features for the August 2026 release, including APIs, mobile, and AEM Widget
jcr-language: en_us
title: Feature availability in Aug 2026 release of Adobe Learning Manager
exl-id: e134937c-630d-4285-9181-2eca114717f6
---

# Feature availability in Aug 2026 release of Adobe Learning Manager

## Purpose

Enterprise customers building or extending the platform through their own front end (a "headless" implementation) regularly ask whether a new or changed feature can actually be used outside the standard web UI, through the Learner API, the Admin API, the AEM Widget, or another integration surface.

This document gives a quick, narrative answer for each feature shipped in this release. For each feature, this document identifies supported application surfaces, integration availability, migration support, and any applicable notification behavior.

## Feature-by-feature availability

### Component-based Email Builder

This will be a phase wise enablement for different accounts who sign-up after the feature release - to migrate those accounts from existing email editor to new editor. Once enabled, customer cannot use old email editor. (For feature enablement, please reach out to CSM/Support).

* **Available on:** Administrator app. Administrators and authors configure email layouts and templates here.
* **Not applicable:** Learner-facing UI, Headless API, and AEM Widget, since learners simply receive the resulting emails through their own mail client.
* **Notifications:**
  * Email notifications continue to be delivered to learners across supported email clients.
  * No new in-platform notification behavior is introduced by this feature.

### External Learning

* **Available on:** Native Web, Headless (Learner) API, Native Mobile Web, and the Administrator app.
* **Not yet available on:** Native Mobile App.
* **Job API:** Not applicable.
* **Migration:** Not yet supported.
* **Notifications:**
  * In-platform notifications are available for learners and managers when external learning approval requests are submitted and when requests are approved or rejected.
  * Email notifications are not currently available for this workflow.

### Incremental User Report

* **Available on:** Job API only. Provides an incremental (delta) export of user data for reporting.
* **Not applicable:** UI, other API surfaces, and migration tooling.

### Report Builder

* **Available on:** Administrator app.
* **Not yet available on:** Job API. A Job-API-based export is planned for a future release.
* **Migration:** Not applicable.
* **Notifications:**
  * Users receive in-platform notifications when report downloads are ready or when report generation fails.
  * Email notifications are not applicable.

### Hierarchical Content Folders

* **Available on:** Administrator app and Author app.
* **Migration:** Supported.
* **Job API:** Not applicable. No dedicated API surface today.

>[!NOTE]
>
>Custom role privileges apply only at the root/parent folder level, not to every folder in the hierarchy.

### Insights Agent

* **Available on:** Administrator app. Currently limited to full admins only (not custom roles).
* **Admin API:** Not available.
* **Job API / Migration:** Not applicable.

### Learning Path Agent

* **Available on:** Native Web and the Headless (Learner) API.
* **Not yet available on:** Native Mobile Web, Native Mobile App, and AEM Widget.
* **Job API / Migration:** Not applicable.

### AI Assistant (Learner)

* **Available on:** Native Web, Headless (Learner) API, and Native Mobile Web.
* **Not yet available on:** Native Mobile App and AEM Widget.
* **Job API / Migration:** Not applicable.

>[!NOTE]
>
>This feature must be explicitly enabled before it appears to learners.

### Live Hub

* **Available on:** Native Web, Headless (Learner) API, Native Mobile Web, and the Administrator app.
* **Job API:** Not applicable.
* **Migration:** Not currently supported.

### Custom Admins: Read/Manage Other Custom Roles

* **Available on:** Administrator app. Lets custom admins view and manage other custom admin roles.
* **Job API / Migration:** Not applicable. No dedicated API for this yet.

### Gradebook

* **Available on:** Native Web, Headless (Learner) API, Native Mobile Web, Native Mobile App, and the Administrator app.
* **Not yet available on:** AEM Widget.
* **Migration:** Not currently supported.
* **Notifications:**
  * No email notifications.
  * No in-platform notifications.

### Channels

* **Available on:** Native Web and the Administrator app. Currently in beta.
* **Not yet available on:** Headless (Learner) API, Mobile Web, Mobile App, AEM Widget, and Admin API.
* **Job API / Migration:** Not applicable.
