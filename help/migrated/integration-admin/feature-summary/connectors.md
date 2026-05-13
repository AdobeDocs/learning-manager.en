---
description: An overview about each ALM-supported connector
jcr-language: en_us
title: Ovreview of ALM-supported connectors
contentowner: mmanuel
---

# Adobe Learning Manager connectors

## Introduction

Adobe Learning Manager (ALM) provides a comprehensive suite of connectors that enable seamless integration with third-party applications and enterprise systems. These connectors serve as bridges between your learning management system and external platforms, facilitating automated data synchronization, user management, content import, and learning record exports.

This document serves as your complete reference guide to understanding and selecting the appropriate connectors for your organization's learning ecosystem. Whether you're looking to integrate with HR systems, eCommerce platforms, virtual meeting tools, or business intelligence solutions.

For an entire list of connectors supported by Adobe Learning Manager, see articles of connectors nested right below this article in the Table of Contents on the left.

>[!NOTE]
>
>This feature is partially available in FedRAMP-authorized environments. See [Feature availability in FedRAMP environments](/help/migrated/feature-availability-in-fedramp-authorized-environment.md) for details.

>[!NOTE]
>
>With the November 2022 release of Adobe Learning Manager, Zoom has deprecated [JWT authentication by June 2023](https://developers.zoom.us/docs/internal-apps/s2s-oauth/). Accordingly, the Zoom connector with JWT will continue to work until mentioned date, but we recommend users to create Server-to-Server OAuth app to replace the functionality in their account. Any new connection will have Zoom OAuth authentication by default.

## Connector categories

Adobe Learning Manager connectors can be organized into several functional categories based on their primary purpose and integration capabilities:

| Category | Purpose | Example Connectors |
|---------|--------|-------------------|
| Data Transfer | File-based data exchange and bulk operations | FTP, Custom FTP, Box |
| Virtual Classroom | Live training and meeting integration | Microsoft Teams, Zoom, Adobe Connect |
| Enterprise Systems | HR and business system integration | Workday, Salesforce, ADFS |
| Content Platforms | External learning content integration | LinkedIn Learning, Harvard ManageMentor, getAbstract |
| Analytics & BI | Reporting and data visualization | Power BI, Training Data Access |
| Authentication | Identity management and security | ADFS (SSO capabilities) |
| eCommerce & Marketing | Sales and marketing integration | Adobe Commerce, Marketo Engage |

## Data transfer and ﬁle management connectors

These connectors facilitate automated data exchange through ﬁle transfer protocols, enabling bulk operations and system-to-system communication.

### Adobe Learning Manager FTP connector

The FTP connector enables organizations to automate data synchronization between Adobe Learning Manager and external systems using the widely adopted File Transfer Protocol. This connector supports secure variants, including SFTP (SSH File Transfer Protocol) and FTPS (FTP Secure) for enhanced security.

#### Key capabilities:

- Upload and download ﬁles between Adobe Learning Manager and remote servers.
- Automated data exchange for user information and training records.
- Support for secure ﬁle transfer protocols (SFTP, FTPS).
- Batch processing of large data sets.

For more information, see [FTP connector](/help/migrated/integration-admin/feature-summary/ftp-connector.md).

### Custom FTP connector

The Custom FTP connector provides more sophisticated ﬁle transfer capabilities, supporting structured data formats and xAPI statement exchanges. This connector is designed for organizations requiring more granular control over their data exchange processes.

#### Key capabilities:

- Import and export user data via structured CSV ﬁles.
- Handle learning records and xAPI statements.
- Automated ﬁle processing from designated FTP folders.
- Enhanced security features for sensitive data transfer.

For more information, see [Custom FTP connector](/help/migrated/integration-admin/feature-summary/custom-ftp-connector.md).

### Box connector

The Box connector leverages Box's cloud storage platform to facilitate seamless data synchronization between external systems and Adobe Learning Manager. This connector is particularly useful for organizations already using Box for ﬁle management.

#### Key capabilities:

- Cloud-based ﬁle storage and synchronization.
- Automated CSV data processing.
- Integration with existing Box workﬂows.
- Real-time data updates from designated folders.

## Virtual classroom and meeting connectors

These connectors integrate Adobe Learning Manager with popular video conferencing and virtual meeting platforms, enabling seamless delivery of live training sessions.

For more information, see [Box connector](/help/migrated/integration-admin/feature-summary/box-connector.md).

### Microsoft Teams connector

The Microsoft Teams connector transforms Adobe Learning Manager into a comprehensive virtual classroom solution by integrating directly with Teams' meeting capabilities. This connector is essential for organizations using Microsoft 365 ecosystem.

#### Key capabilities:

- Schedule virtual classroom sessions directly from Adobe Learning Manager.
- Automatic Teams meeting creation and management.
- Seamless learner access without separate meeting links.

For more information, see [MS Teams connector](/help/migrated/integration-admin/feature-summary/install-microsoft-teams-connector.md).

### Zoom connector

The Zoom connector enables organizations to leverage Zoom's robust video conferencing capabilities directly within their Adobe Learning Manager environment, providing a seamless experience for both instructors and learners.

#### Key capabilities:

- Direct Zoom meeting scheduling from Adobe Learning Manager.
- Automated meeting link generation and distribution.
- Real-time attendance monitoring.
- Recording management and playback integration.
- Breakout room support for interactive sessions.

For more information, see [Zoom connector](/help/migrated/integration-admin/feature-summary/zoom-connector.md).

### Adobe Connect connector

The Adobe Connect connector provides deep integration with Adobe's own virtual classroom platform, oﬀering advanced features for interactive online learning experiences.

#### Key capabilities:

- Advanced interactive features (polls, quizzes, breakouts).
- High-quality screen sharing and presentation tools.
- Comprehensive session recording and playback.
- Mobile-optimized virtual classroom experience.

For more information, see [Adobe Connect connector](/help/migrated/integration-admin/feature-summary/adobe-connect-connector.md).

## Enterprise system integration connectors

These connectors enable Adobe Learning Manager to integrate with core business systems, facilitating automated user management and organizational data synchronization.

### Workday connector

The Workday connector creates a seamless bridge between your HR system and learning management platform, ensuring that employee records, organizational structures, and role assignments remain synchronized across both systems.

#### Key capabilities:

- Automated user provisioning from Workday.
- Real-time employee data synchronization.
- Organizational hierarchy mapping.
- Role-based learning assignment automation.

For more information, see [Workday connector](/help/migrated/integration-admin/feature-summary/workday-connector.md).

### Salesforce connector

The Salesforce connector enables organizations to integrate their customer relationship management system with learning initiatives, creating opportunities for sales training, customer education, and performance tracking.

#### Key capabilities:

- Automated user import from Salesforce.
- Custom data ﬁeld mapping.
- Learning record export to Salesforce.
- Sales performance correlation with training completion.
- Customer education program management.

For more information, see [Salesforce connector](/help/migrated/integration-admin/feature-summary/salesforce-connector.md).

### ADFS (Active Directory Federation Services) connector

The ADFS connector enables organizations to implement enterprise-grade authentication and authorization, allowing users to access Adobe Learning Manager using their existing Active Directory credentials.

#### Key capabilities:

- Single Sign-On (SSO) implementation
- Enterprise security compliance
- Seamless user authentication

For more information, see [ADFS connector](/help/migrated/integration-admin/feature-summary/adfs-connector.md).

## Content and learning platform connectors

These connectors expand your learning catalog by integrating external content libraries and specialized learning platforms.

### LinkedIn Learning connector

The LinkedIn Learning connector provides access to LinkedIn's extensive library of professional development courses, allowing organizations to supplement their internal training with industry-leading external content.

#### Key capabilities:

- Access to LinkedIn Learning's complete course catalog.
- Automated course discovery and import.
- Learner progress tracking within Adobe Learning Manager.

For more information, see [LinkedIn connector](/help/migrated/integration-admin/feature-summary/linkedin-learning-connector.md).

### Harvard ManageMentor connector

The Harvard ManageMentor connector brings world-class leadership and management training content directly into your Adobe Learning Manager environment, providing access to Harvard Business School's renowned educational resources.

#### Key capabilities:

- Premium Harvard Business School content access.
- Management and leadership development modules.
- Seamless content import and organization.

For more information, see [Harvard ManageMentor connector](/help/migrated/integration-admin/feature-summary/harvard-managementor-connector.md).

### getAbstract Connector

The getAbstract connector provides access to concise business book summaries and professional insights, enabling organizations to oﬀer continuous learning through digestible content formats.

#### Key capabilities:

- Access to business book summaries and insights.
- Usage data tracking and reporting.
- Automated completion record creation.

For more information, see [getAbstract connector](/help/migrated/integration-admin/feature-summary/getabstract-connector.md).

## Business intelligence and analytics connectors

These connectors enable advanced reporting, data visualization, and business intelligence capabilities by integrating learning data with external analytics platforms.

### Power BI connector

The Power BI connector transforms your learning data into actionable business insights by automatically synchronizing learning metrics with Microsoft's powerful business intelligence platform.

#### Key capabilities:

- Real-time learning data synchronization.
- Custom dashboard creation and management.
- Advanced data visualization and reporting.
- Learner transcript and skill report integration.

For more information, see [Power BI connector](/help/migrated/integration-admin/feature-summary/power-bi-connector.md).

### Training Data Access connector

The Training Data Access connector enables organizations to create custom learning interfaces and headless learning experiences by providing API access to training data and course information.

**Key capabilities:**

- Public API access to course and learning path data.
- Custom user interface development support.
- Headless learning experience creation.
- Advanced search and ﬁltering capabilities.

For more information, see [Training Data Access connector](/help/migrated/integration-admin/feature-summary/training-data-access-connector.md).

## eCommerce and marketing connectors

These connectors enable monetization of learning content and integration with marketing automation platforms.

### Adobe Commerce connector

The Adobe Commerce connector transforms Adobe Learning Manager into a comprehensive learning commerce platform, enabling organizations to sell courses, certiﬁcations, and training programs through a fully integrated eCommerce experience.

**Key capabilities:**

- Seamless eCommerce platform integration.
- Course catalog and pricing management.
- Automated payment processing and enrollment.

For more information, see [Adobe Commerce connector](/help/migrated/integration-admin/feature-summary/adobe-commerce-connector.md).

### Marketo Engage connector

The Marketo Engage connector creates powerful synergies between learning activities and marketing campaigns, enabling organizations to leverage educational engagement for lead nurturing and customer development.

#### Key capabilities:

- Automated lead creation and updates.
- Learning activity tracking for marketing insights.
- Course enrollment and completion event triggers.

For more information, see [Marketo Engage connector](/help/migrated/integration-admin/feature-summary/marketo-engage-connector.md).
