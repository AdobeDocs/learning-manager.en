---
description: Learn about the new features and enhancements in the April 2026 release of Adobe Learning Manager
jcr-language: en_us
title: What's new in Adobe Learning Manager April 2026 release
---

# What's new in Adobe Learning Manager April 2026 release

**For learners:** The Fluidic Player now shows the next module name and a clear Exit button. Player language can be set via LTI for a consistent experience across platforms. The custom parameter name is 'locale' and it accepts the locale code. For example, locale=fr-FR. Captivate content includes a unified table of contents, slide-level completion ticks, and reliable notes exports. Multi-language support is available for Job Aids, checklist questions, and video text tracks (VTT). The AI Assistant helps learners get answers within the learning experience.

**For administrators and authors:** The Zoom Connector supports multiple concurrent VILT sessions. Shared courses in peer accounts display the real author instead of "External Author." Admins can restrict when modules can be started. Learning Object expiry dates are exposed in Learner APIs. Checklist modules support weighted scoring, multilingual question text, and optional reviewer comments. Custom certificates offer a drag-and-drop editor with dynamic fields and AI-generated backgrounds. The non-logged-in Experience Builder lets you build public learning pages without requiring login.

**For instructors:** Generate QR codes for instance enrollment and session attendance. Add comments or feedback during checklist evaluation.

**Reporting and analytics:** SCORM content can now report multiple quiz attempts in L2 reporting. Learning time spent calculation is improved in Learner Transcripts. Learning Transcript reports for Administrators are updated. Advanced search enhancements are available.

**Log-in method:** Learn how OpenID Connect sign-in works in Adobe Learning Manager for learners, authors, and administrators. OpenID Connect (OIDC) is a common sign-in method built on web standards. Many organizations use
an identity provider (for example, Okta, Google Workspace, or Microsoft Entra ID) for employees and partners.

View [log in with OIDC](/help/migrated/oidc.md) for more information.

## Webhooks and migration in Alternates and Equivalents

### Webhooks

When a learner completes a course via an alternate or relationship, ALM triggers a webhook event that is separate from the standard course completion webhook. This ensures that integrations can respond differently to alternate completions where required. Webhook events are also triggered when retroactive completion or retroactive incompletion occurs, covering historical updates as well as relationship changes.

View [Webhooks](/help/migrated/integration-admin/feature-summary/webhooks.md#webhooks-for-alternates) for more information.

### Migration

The CSV-based data model and migration behavior for introducing learning object (LO) equivalence in the system is outlined in [Webhooks](/help/migrated/integration-admin/feature-summary/migration-manual.md#migration-for-alternates-and-equivalents).

## Auto-purge of deleted users

The Auto-purge of deleted users is a feature that purges data for users who have already been deleted in ALM. Purging happens after a configurable retention period, focusing on bulk operations so large customer accounts can be handled efficiently without hurting performance.

View [Auto purge of deleted users](/help/migrated/administrators/feature-summary/purge-users.md#auto-purge-of-deleted-users) for more information.

## Set module access time control

The enhancement lets authors and administrators in Adobe Learning Manager define a time window during which learners are allowed to start a module. Outside the configured start/end window, the module remains visible in the course structure, but learners cannot initiate it.

View [Set module access time control](/help/migrated/administrators/feature-summary/module-access-time-control.md) for more information.

## Changes to Learner Transcripts

This release enhances the Learning Transcripts (LT) report with clearer auditability and compliance support. 

* A new Completion Method column in the admin LT shows whether completions were direct, alternate, or revoked, while alternate completions now influence status, completion date, and completion source using inherited dates from source trainings and updating when sources are revoked or direct completions occur. 
* Revoked alternates automatically adjust status, completion date, and completion source when all qualifying relationships are removed with retroactive incompletion enabled. 
* Reviewer feedback from checklist modules is standardized under the renamed Reviewer's remarks column across admin and learner LTs and all export channels. 
* Finally, learning time calculations now better distinguish active versus idle time, improving the accuracy of engagement and compliance reporting.

View [Changes in Learner Transcript report](/help/migrated/administrators/feature-summary/reports/changes-in-learner-transcript.md) for more information. 

## Checklist with commenting capability for reviewer

This feature lets reviewers add comments or feedback during checklist evaluation. You can provide personalized, actionable feedback for each learner. You can also choose to display your name with your comments for transparency. All remarks are saved in the learner's transcript and included in checklist reports.

View [Configure checklist with commenting](/help/migrated/authors/feature-summary/courses.md#checklist-with-commenting) for more information.

## Multi-language support for checklist

This feature lets you create and manage checklist modules in multiple languages. Each checklist question, instruction, and evaluation criterion can be translated so reviewers and learners interact with the checklist in their preferred language. The system displays the checklist in the user's selected content language, which improves accessibility and compliance for global teams.

View [Create multi-language checklist in modules](/help/migrated/authors/feature-summary/courses.md#create-a-multi-language-checklist)

## Checklist question weightage for instructor evaluations

This feature lets you assign different maximum scores (weightage) to each checklist question. You can reflect the varying importance or difficulty of each question, which supports more accurate and meaningful evaluations. The system calculates the total score based on your input and determines if the learner passes or fails according to the criteria you set.

View [Create weighted checklist questions](/help/migrated/authors/feature-summary/courses.md#how-to-create-a-weighted-checklist)

## Custom certificates

Custom Certificates in Adobe Learning Manager (ALM) let administrators and authors design, manage, and issue personalized certificates for learners.

The feature includes a drag-and-drop editor, dynamic fields, multilingual support, and AI-generated backgrounds, enabling organizations to create branded certificates without technical expertise.

View [Design custom certificates](/help/migrated/administrators/feature-summary/create-customize-certificate.md)

## Non-logged in experience in Experience Builder

The non-logged-in experience in Experience Builder allows organizations to display their learning content and portal pages to all visitors, including those who have not signed in. This feature is designed to attract, inform, and engage prospective learners by offering a smooth and branded preview of your training offerings before requiring them to log in or enroll.

View [Non-logged in experience in Experience Builder](/help/migrated/administrators/feature-summary/experience-builder/non-logged-in-experience.md)

## Advanced search enhancements

Search results in Advanced Search are now more accurate and relevant. Exact keyword matches are ranked higher across both in-content search & metadata making it easier for learners to find precisely what they are looking for.

Learners can now also see enrolled Learning Objects in search results, even if they are not part of an accessible catalog — ensuring no relevant content is missed. Additionally, Job Aid ranking has been improved across both Advanced Search and within-content search, surfacing the most relevant resources faster.

## Multi-lingual job aids

Multilingual Job Aids in Adobe Learning Manager (ALM) let authors and administrators provide supporting documents, guides, or resources in multiple languages within a single job aid entry. Learners across different regions can access relevant materials in their preferred language, which improves comprehension, compliance, and user experience.

View [Add multi-lingual job aids](/help/migrated/authors/feature-summary/job-aids.md#create-a-multilingual-job-aid) for more information.

## Multi-lingual Video Text Tracks (VTT) support (for authors)

Multi-lingual Video Text Tracks (VTT) support in Adobe Learning Manager enables authors to provide subtitles and captions for video and audio content in multiple languages. This feature streamlines localization, making training accessible to a global audience and ensuring compliance with accessibility standards. Authors can auto-generate, translate, review, and edit VTT files directly within the platform.

View [Multi-lingual VTT support](/help/migrated/authors/feature-summary/content-library.md#multi-lingual-vtt-support) for more information.

## Show original author for shared courses in peer accounts

When a course is shared through the catalog to a peer account, Adobe Learning Manager currently labels the author as "External Author" in the Learner, Administrator, and Author views of the receiving account. This can create challenges for learners and administrators, particularly in large enterprises, as it becomes difficult to identify and contact the appropriate content owner when issues or questions arise.

The enhancement ensures that author information is preserved and surfaced for shared courses in peer accounts, rather than being replaced by a generic placeholder.

### What's new

Show actual author name for shared courses in peer accounts

For courses shared via external or peer catalogs, the original author name from the source account is now displayed in the receiving account instead of "External Author".

This applies to:

* Learner app (course card or course details).
* Administrator and author views when previewing as a learner.

View [Author name display for shared courses](/help/migrated/administrators/feature-summary/peer-account.md#author-name-display-for-shared-courses-including-previously-acquired-courses) for more information.

## Equivalents and alternates

Deliver a frictionless learning experience and eliminate redundant training with Equivalents and Alternates in ALM. This new capability allows admins to configure one-way (alternates) or bidirectional (equivalents) rules, where completing one training automatically grants alternate completion for another. Designed to streamline large learning ecosystems, this feature ensures learners bypass content they've already mastered, and organizations drastically reduce admin support tickets, eliminate manual overrides, and maintain a cleaner, more accurate learner record.

View [Equivalents and alternates](/help/migrated/administrators/feature-summary/alternates-equivalence.md) for more information.

## Instructor QR codes for instance enrollment and session attendance

Instructors can generate QR codes themselves for:

- Course instance enrollment,
- Session attendance, or
- Enrollment + attendance together

at the session level. It's designed for situations where learners enter a physical or hybrid classroom and require a quick, self-service option to enroll and record their attendance using a QR code.

View [Download QR codes for learner enrollment and attendance](/help/migrated/instructors/feature-summary/learners.md#download-qr-codes-for-learner-enrollment-and-attendance) for more information.

## Calendar invites (ICS) with session links

Adobe Learning Manager includes the **session join link directly in calendar invites (ICS files)** sent to learners and instructors. This allows participants to join sessions directly from their calendar without searching for the session email.

This enhancement improves the experience for calendar clients such as **Gmail** and **Outlook**.

View [Calendar invites with session links](/help/migrated/instructors/feature-summary/learners.md#joining-a-session-from-gmail) for more information.

## AI Assistant for learners

The AI Assistant (Beta) for learners helps them quickly find answers from the assigned learning content without browsing through entire courses. You can ask questions in plain language and receive accurate, focused responses with source links to the relevant course content.

Capabilities, supported scenarios, and limitations may change as the feature evolves. The AI Assistant is a generative AI-powered chat companion in Adobe Learning Manager that delivers quick, accurate answers using your trusted learning content. It includes citations so you always know the source of the information.

View [AI Assistant for ll](/help/migrated/learners/feature-summary/learner-ai-assistant.md)


## API changes in the release

The April 2026 release of Adobe Learning Manager introduces focused enhancements to the Public API around alternates and equivalents, time‑windowed access to content, content‑driven quiz attempts, non‑logged‑in experiences, and Job Aid handling. The changes are designed to be largely backward‑compatible while enabling more precise integrations.

View [API changes in the April release](/help/migrated/api-changes-alm.md)

## System requirements

View [Adobe Learning Manager system requirements](/help/migrated/system-requirements.md).

## Release notes

Check out the [release notes](/help/migrated/release-note/release-notes.md) for latest release updates. 

## Previous releases of Adobe Learning Manager

- [Adobe Learning Manager May 2025 release](/help/migrated/whats-new-may-2025.md)
