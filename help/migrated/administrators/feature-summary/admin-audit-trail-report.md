---
description: Learn how the Administrator Audit Trail Report tracks configuration changes, showing who made them, when, and the values before and after.
jcr-language: en_us
title: Administrator Audit Trail Report
exl-id: 71b2ee42-ef1c-47fb-95ad-c339562e227d
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
---

# Administrator Audit Trail Report {#adminaudittrailreport}

Generate a report of configuration changes made to your account's Basics, Advanced, and Integration settings — including who made each change, when, and the value before and after.

## What the report captures

The Administrator Audit Trail Report gives you a historical record of configuration changes so you can determine:

- Who made the change
- When the change was made
- What the setting was before the change
- What the setting is after the change

The report covers changes made to:

- **Basics** settings
- **Advanced** settings
- **Integrations** settings

The report is additive-only: new change records are added over time, and previously recorded entries are never removed. This lets you review the full history of a setting across multiple changes, not just its current value.

The report is available to any user with Report privileges and full user group access. This includes full Administrators and custom Administrators who have been granted Report access.

>[!NOTE]
>
>Records are available starting from Update 112, September 2026. Changes made before this update are not included in the report. See [release notes](/help/migrated/release-note/release-notes.md) Update 112.

## Why this report matters for compliance

Organizations operating in regulated industries often need to demonstrate that configuration changes to systems handling electronic records are tracked, attributable, and retained. The Administrator Audit Trail Report supports these requirements by identifying the person, setting, time, and before-and-after values for each change.

>[!NOTE]
>
>This report supports your organization's compliance activities. It does not, by itself, certify compliance with any specific regulation or standard.

## Generate an Administrator Audit Trail Report

1. Sign in to Adobe Learning Manager as an Administrator.
2. In the left navigation, select **Manage** > **Reports** > **Custom Reports**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report1.png)

3. Scroll down and select **Administrator Audit Trail**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report2.png)

4. **Select Range**: choose the period to report on — **Last one week**, **Last one month**, or **Choose dates**. If you select **Choose dates**, enter a **From** date and a **To** date.
5. **Select setting type**: choose **Select All**, **Basics**, **Integrations**, or **Advanced**.

   To see the complete list of settings tracked by this report across Basics, Integrations, and Advanced, select **Download List of settings**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report6.png)

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report3.png)

6. Select **Generate**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report4.png)

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report5.png)

A `.csv` file containing the changes downloads to your browser's Downloads folder. Report generation may take a few moments — you can continue using Adobe Learning Manager while it processes. If you close the browser window before the report is ready, the download begins the next time you sign in.

## Common uses for this report

- **Investigate an unexpected setting change** — confirm what changed, when, and who made the change, rather than relying on assumptions.
- **Review changes made by multiple Administrators** — generate a consolidated view of all configuration activities which are in scope of the report for a given period, instead of contacting each Administrator individually.
- **Confirm an approved configuration change** — verify that the expected Administrator made the change, within the expected time period, and that the new value matches what was approved.
- **Compare a setting's history over multiple changes** — use the **Revision** column to see how many times a specific setting has changed and review each recorded value in sequence, including whether a later change restored an earlier one.
- **Support a compliance review** — generate the report for the period under review as part of your administrative and compliance records.
- **Review settings after a policy change** — confirm that intended configuration updates were applied consistently, and identify any changes that occurred unexpectedly.
- **Maintain a historical administrative record** — download and retain reports according to your organization's record-management practices.

## Report column reference

The downloaded `.csv` file includes the following columns.

| Column | Description |
|---|---|
| **Event ID** | A unique identifier for this specific change record. |
| **Timestamp (UTC)** | The date and time the change was made, in Coordinated Universal Time. |
| **Email** | The email address of the Administrator who made the change. |
| **UUID** | A unique identifier for the Administrator who made the change. Populated only if UUID is enabled at the account level. |
| **Admin Name** | The display name of the Administrator who made the change. |
| **Event Type** | The category of event recorded — for example `Modify`, `Create`, or `Delete`. |
| **Action Type** | The type of action performed on the setting — for example, `CREATE_SETTING`, `UPDATE_SETTING`, or `DELETE_SETTING`. |
| **Object Type** | The setting or configuration object that was changed. |
| **Object ID** | The unique identifier of the specific setting or configuration object that was changed. |
| **Previous Value** | The value of the setting before the change. (For a deleted setting, this shows the value that existed before deletion.) |
| **New Value** | The value of the setting after the change. (For a deleted setting, this is blank.) |
| **Revision** | The number of times this specific Object ID has been changed when the event is recorded. The first recorded change for an object starts at 1. |

>[!TIP]
>
>To find all settings that were deleted during a period, filter the downloaded file where **Action Type** is `DELETE_SETTING`.

## Access this report programmatically

You can retrieve the Administrator Audit Trail Report programmatically using the Jobs API, rather than generating it manually from the Admin app. This is useful if you want to schedule regular exports or feed the report into a downstream monitoring or alerting system. See [Jobs API Admin Audit Trail Report](/help/migrated/api-changes-sep-2026.md#job-api-for-admin-audit-trail-report).

## Limitations

- **Localization**: Report content is not localized. The report is generated in the default account language regardless of your account's configured locale settings.
- **Reason for change**: The report does not capture why a change was made. Retain any related change request, approval, or business justification separately.

## Best practices

- Select a date range that covers the suspected or planned change.
- Select **Select All** when the affected settings area is not known.
- Compare both the **Previous Value** and **New Value** columns for each entry.
- Use the **Admin Name** and **Timestamp** columns to correlate a change with approved work or internal records.
- Keep the related change request, approval, or business justification separately when your organization requires a documented explanation for a change.

## Troubleshooting

**I don't see any records before a certain date**
Records are available only from Update 112 (September 2026) onward. Changes made before that update are not included in the report. See [release notes](/help/migrated/release-note/release-notes.md)

**The UUID column is empty for some or all records**
The UUID column is populated only if UUID is enabled at the account level. If it is not enabled, this column will not be present.

**I have a custom Administrator role, but I can't find this report**
Confirm that your custom role has been granted Report privileges and full user group access. Contact your account owner or a full Administrator to request this access if needed.
