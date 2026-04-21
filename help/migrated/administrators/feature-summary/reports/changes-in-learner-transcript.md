---
description: Learn about Learner Transcripts
jcr-language: en_us
title: Changes to Learner Transcripts
exl-id: 295c4e1f-c3c7-4f97-83c3-1234f3d47546
---
# Changes to Learner Transcripts in the April release

## Completion Method column

The **Completion Method** column indicates how each record in the administrator's Learner Transcript was completed.

**Values:**

1. **Direct** (for direct completions)
2. **Alternate** (for completions achieved via alternate relationships)
3. **Alternate Revoked** (when all alternate completions are revoked due to retroactive incompletion and relationship removal)

>[!NOTE]
>
>This column is not visible in the learner's LT; it is only available in the admin LT for reporting and tracking purposes. 

**Impact**: Enables clear audit trails, compliance tracking, and transparency for administrators regarding how a course was completed.

## Alternate completion tracking in Learner Transcripts

Alternate completions allow learners to receive completion credit for a target course or learning path when they have completed an equivalent source course or path, based on established relationships.

In the Learner Transcript (LT), alternate completions impact three existing columns: **Status**, **Completion Date**, and **Completion Source**.

- **Status**: The status can be **Completed** even if the learner has not directly completed the target course or path due to alternate completion. Other statuses (**Not Started**, **In Progress**, **Unenrolled**) are not affected.
- **Completion Date**: For alternate completion, the date is inherited from the source course or path. If the learner later completes the target directly, the date updates to reflect the direct completion.
- **Completion Source**: Captures the training ID(s) of the source course(s) or path(s) that provided the alternate completion. Multiple active sources are listed as comma-separated IDs. If sources are revoked, only active ones remain. When multiple sources exist, the earliest completion date is used.

**Impact**: Alternate completions reduce manual reconciliation, automate progress tracking in learning paths and certifications, and support compliance requirements.

>[!NOTE]
>
>Learner Transcripts do not display the **Completion Method** column. This column is available only in the admin Learner Transcript.

## Completion date logic for alternates

The **Completion Date** column in the Learner Transcript is used for both direct and alternate completions.

- For alternate completions, the date reflects when the learner completed the source course or path.
- If the learner later completes the target directly, the completion date is updated to the direct completion date.
- No new column is introduced for alternate completion dates.
- If multiple sources provide alternate completion, the earliest active completion date is used.
- If a source is revoked (with retroactive incompletion enabled), the date updates to the next earliest active source or is cleared if no active sources remain.

**Impact**: Ensures accurate historical tracking and consistent reporting, even when alternate relationships change over time.

## Revoked alternate completions

Revoked alternate completions occur when all source relationships for a target course or learning path are removed, provided retroactive incompletion is enabled.

### Trigger conditions

- Retroactive incompletion must be enabled at the account level.
- Revocation occurs only when **all** active source relationships are removed.
- If at least one source remains, the alternate completion persists and the completion source column updates accordingly.

### Impact on Learner Transcript

- **Status**: If all alternate completions are revoked and there is no direct completion, the status updates (for example, from **Completed** to **Not Started** or **In Progress**).
- **Completion Date**: Cleared if no active sources remain and there is no direct completion.
- **Completion Source**: Updated to remove revoked sources; cleared if all sources are revoked.

If the learner has a direct completion, revoking alternate sources does not affect completion status or completion date.

>[!NOTE]
>
>If multiple sources provided alternate completion and only some are revoked, the transcript reflects remaining active sources and their earliest completion date. If all sources are revoked and there is no direct completion, the learner loses completion status for the target.

## Enhanced reporting for checklist reviewer remarks

Reviewer comments from checklist modules are now included in the Learner Transcript report under a renamed column called **Reviewer Remarks.**

| Area | Old column name | New column name | Notes |
|------|-----------------|-----------------|-------|
| Learner Transcripts (Admin) | Submission comment | Reviewer's remarks  | Applies to all Admin LT sources: UI, Job API, Connectors.| 

This change applies uniformly to all Admin LT sources (UI exports, Job API reports, and connectors where applicable). Connector‑exported LT will surface Reviewer's remarks as a dedicated column at the end (for connectors that did not previously expose Submission comment), ensuring downstream integrations can distinguish reviewer feedback from other comments.

**Impact:** Enables learners and administrators to view consolidated feedback, improving transparency and supporting performance evaluation.

>[!NOTE]
>
>For the Learner Transcripts for learners, the column previously labeled **Submission comment** is now renamed to **Reviewer's remarks**, and populated with the checklist reviewer's comment when enabled.

## Improved learning time calculation

The Learner Transcript report now uses refined logic to distinguish between active and idle learning time based on user activity and browser tab focus.

**Impact**: Provides more accurate measurement of learner engagement, supporting compliance reporting and analytics.
