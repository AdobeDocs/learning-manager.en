---
description: Learn about the new features and enhancements in the April 2026 release of Adobe Learning Manager
jcr-language: en_us
title: What's new in Adobe Learning Manager April 2026 release
---

# What's new in Adobe Learning Manager April 2026 release

**For learners:** The Fluidic Player now shows the next module name and a clear Exit button. Player language can be set via LTI for a consistent experience across platforms. Captivate content includes a unified table of contents, slide-level completion ticks, and reliable notes exports. Multi-language support is available for Job Aids, checklist questions, and video text tracks (VTT). The AI Assistant helps learners get answers within the learning experience.

**For administrators and authors:** The Zoom Connector supports multiple concurrent VILT sessions. Shared courses in peer accounts display the real author instead of "External Author." Admins can restrict when modules can be started. Learning Object expiry dates are exposed in Learner APIs. Checklist modules support weighted scoring, multilingual question text, and optional reviewer comments. Custom certificates offer a drag-and-drop editor with dynamic fields and AI-generated backgrounds. The non-logged-in Experience Builder lets you build public learning pages without requiring login.

**For instructors:** Generate QR codes for instance enrollment and session attendance. Add comments or feedback during checklist evaluation.

**Reporting and analytics:** SCORM content can now report multiple quiz attempts in L2 reporting. Learning time spent calculation is improved in Learner Transcripts. Learning Transcript reports for Administrators are updated. Advanced search enhancements are available.

## Auto-purge of deleted users

The Auto-purge of deleted users is a feature that purges data for users who have already been deleted in ALM. Purging happens after a configurable retention period, focusing on bulk operations so large customer accounts can be handled efficiently without hurting performance.

View [Auto purge of deleted users](/help/migrated/administrators/feature-summary/purge-users.md#auto-purge-of-deleted-users) for more information.

## Changes to Learner Transcripts

### Completion Method column

The **Completion Method** column indicates how each record in the administrator's Learner Transcript was completed.

**Values:**

1. **Direct** (for direct completions)
2. **Alternate** (for completions achieved via alternate relationships)
3. **Alternate Revoked** (when all alternate completions are revoked due to retroactive incompletion and relationship removal)

>[!NOTE]
>
>This column is not visible in the learner's LT; it is only available in the admin LT for reporting and tracking purposes. 

**Impact**: Enables clear audit trails, compliance tracking, and transparency for administrators regarding how a course was completed.

### Alternate completion tracking in Learner Transcripts

Alternate completions allow learners to receive completion credit for a target course or learning path when they have completed an equivalent source course or path, based on established relationships.

In the Learner Transcript (LT), alternate completions impact three existing columns: **Status**, **Completion Date**, and **Completion Source**.

- **Status**: The status can be **Completed** even if the learner has not directly completed the target course or path due to alternate completion. Other statuses (**Not Started**, **In Progress**, **Unenrolled**) are not affected.
- **Completion Date**: For alternate completion, the date is inherited from the source course or path. If the learner later completes the target directly, the date updates to reflect the direct completion.
- **Completion Source**: Captures the training ID(s) of the source course(s) or path(s) that provided the alternate completion. Multiple active sources are listed as comma-separated IDs. If sources are revoked, only active ones remain. When multiple sources exist, the earliest completion date is used.

**Impact**: Alternate completions reduce manual reconciliation, automate progress tracking in learning paths and certifications, and support compliance requirements.

>[!NOTE]
>
>Learner Transcripts do not display the **Completion Method** column. This column is available only in the admin Learner Transcript.

### Completion date logic for alternates

The **Completion Date** column in the Learner Transcript is used for both direct and alternate completions.

- For alternate completions, the date reflects when the learner completed the source course or path.
- If the learner later completes the target directly, the completion date is updated to the direct completion date.
- No new column is introduced for alternate completion dates.
- If multiple sources provide alternate completion, the earliest active completion date is used.
- If a source is revoked (with retroactive incompletion enabled), the date updates to the next earliest active source or is cleared if no active sources remain.

**Impact**: Ensures accurate historical tracking and consistent reporting, even when alternate relationships change over time.

### Revoked alternate completions

Revoked alternate completions occur when all source relationships for a target course or learning path are removed, provided retroactive incompletion is enabled.

#### Trigger conditions

- Retroactive incompletion must be enabled at the account level.
- Revocation occurs only when **all** active source relationships are removed.
- If at least one source remains, the alternate completion persists and the completion source column updates accordingly.

#### Impact on Learner Transcript

- **Status**: If all alternate completions are revoked and there is no direct completion, the status updates (for example, from **Completed** to **Not Started** or **In Progress**).
- **Completion Date**: Cleared if no active sources remain and there is no direct completion.
- **Completion Source**: Updated to remove revoked sources; cleared if all sources are revoked.

If the learner has a direct completion, revoking alternate sources does not affect completion status or completion date.

>[!NOTE]
>
>If multiple sources provided alternate completion and only some are revoked, the transcript reflects remaining active sources and their earliest completion date. If all sources are revoked and there is no direct completion, the learner loses completion status for the target.


### Enhanced reporting for checklist reviewer remarks

Reviewer comments from checklist modules are now included in the Learner Transcript report under a renamed column, **Reviewer Remarks**.

**Impact**: Enables learners and administrators to view consolidated feedback, improving transparency and supporting performance evaluation.

### Improved learning time calculation

The Learner Transcript report now uses refined logic to distinguish between active and idle learning time based on user activity and browser tab focus.

**Impact**: Provides more accurate measurement of learner engagement, supporting compliance reporting and analytics.

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

View [Non-logged in experience in Experience Builder](/help/migrated/administrators/feature-summary/non-logged-in-experience-learners.md)

## System requirements

View [Adobe Learning Manager system requirements](/help/migrated/system-requirements.md).

## Release notes

Check out the [release notes](/help/migrated/release-note/release-notes.md) for latest release updates. 

## Previous releases of Adobe Learning Manager

<<<<<<< Updated upstream
* [Adobe Learning Manager May 2025 release](/help/migrated/whats-new-may-2025.md)
* [Adobe Learning Manager November 2025 release](/help/migrated/whats-new-nov-24.md)


=======
- [Adobe Learning Manager October 2025 release](/help/migrated/whats-new-october-2025.md)
- [Adobe Learning Manager May 2025 release](/help/migrated/whats-new-may-2025.md)
>>>>>>> Stashed changes
