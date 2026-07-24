---
jcr-language: en_us
title: Submit external learning in Adobe Learning Manager
description: Managers can review external learning requests submitted by their team members, verify the details and any proof of completion, and approve or reject each request with an optional comment. Approved submissions are added to the Learner Transcript. 
contentowner: saghosh
---

# Review external learning requests as a manager

When a learner on your team submits an external learning request in Adobe Learning Manager, you receive an in-platform notification. You can review the submission details, approve or reject the request, and add a comment for the learner.

## How the manager review workflow works

When a learner submits an external learning request, the following happens:

1. You receive an **in-app notification** prompting you to review the submission. The submission appears in the **External Learning** tab on your manager dashboard.
2. You open a submission, review all fields and any uploaded document as proof, and select **Approve** or **Reject**.
3. You can add a **review comment** that the learner sees when they receive their notification.
4. The learner receives an **in-platform notification** with your decision.

If you approve a submission, the external learning activity is added to the **Admin Learner Transcript** and appears in the learner's transcript record.

<!--You can also change a previously **Rejected** submission to **Approved** if the circumstances change.-->

## Review and approve or reject a submission

1. Sign in to Adobe Learning Manager as a manager.

2. Select **External Learning** in the left navigation pane.

3. In the submission list, select the request you want to review. Submissions are sorted by submitted date, with the most recent at the top.

4. Review the full submission:

    - Title, description, dates, duration, and score

    - Any custom fields configured by your administrator

    - The attached proof document, if provided. Select the attachment to view or download it

5. Select **Approve** or **Reject**.

6. In the **Review Comment** field, enter any notes for the learner. This is optional but recommended when rejecting a request, so the learner understands what to correct.

7. Select **Submit**.

The learner receives an in-app notification of your decision. If you approved the submission, it now appears in the Learner Transcript.

## Manage your submission queue

Your External Learning queue shows all pending and past submissions from your direct reports.

**Filter by status**

Use the **Status** filter to narrow the list:

- **All**- shows every submission regardless of status

- **Awaiting review-** shows only submissions pending your review

- **Approved-** shows submissions you have already approved

- **Rejected-** shows submissions you have rejected

**Search and sort**

- Use the **Search** field to find submissions by learner name.

- Submissions are sorted by submitted date by default, with the most recent at the top.

### Approval routing rules

By default, external learning submissions are routed to a learner's direct manager. The following rules apply when a learner does not have a direct manager assigned:

| **Learner has a manager** | **Learner is a manager themselves** | **Submission is routed to**                                                                                         |
|---------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Yes                       | No                                  | Direct manager (default case)                                                                                       |
| Yes                       | Yes                                 | Direct manager (default case)                                                                                       |
| No                        | No                                  | Root account user, if the root account user has a manager role; otherwise, the submission is auto-approved.         |
| No                        | Yes                                 | Root account user, if the root account user has a manager role; otherwise, the submission is routed to the learner. |

If you have questions about the manager assignment for a specific learner, contact your account administrator.

## External learning reporting and transcript changes

When a learner's external learning submission is approved in Adobe Learning Manager, the activity is added to the reporting system and appears in both the Admin Learner Transcript and the Learner Transcript.

### How external learning appears in Learner Transcripts

**Note:** Enabling External Learning adds the following new columns to the Admin Learner Transcript: **External Learning Name**, **Completion Comment**, and a dynamic column for each custom field. Custom field columns always appear at the end of the export. If Learner Transcript data feeds into automated reporting or BI tools, ensure those pipelines are updated to handle the additional columns.

Only **approved** external learning submissions appear in transcripts. Submissions in **Awaiting Approval** or **Rejected** status are not included in transcript exports.

The Admin Learner Transcript and the Learner Transcript handle the external learning title differently:

- In the **Admin Learner Transcript**, the external learning title is placed in the existing **LP/Certification/Course** column, keeping the column structure consistent with other learning activity types.

- In the **Learner Transcript** (learner-generated), a new column called **External Learning Name** is added immediately after the **Module** column.

Custom fields configured by your administrator appear as dynamic columns at the end of both transcript exports once a submission is approved.

Date-based filtering in the Admin Learner Transcript for external learning rows is based on the **completion date**, which corresponds to the approval date.