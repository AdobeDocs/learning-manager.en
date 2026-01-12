---
jcr-language: en_us
title: Troubleshoot Salesforce (SFDC) integration issues with Adobe Learning Manager
description:  troubleshoot common Salesforce (SFDC) integration issues with Adobe Learning Manager (ALM), including failed exports, field permission problems in SFDC custom objects, and important SFDC–ALM compatibility notes.
contentowner: saghosh
---

## Troubleshoot SFDC export failures (no export for 2–3+ hours)

If the SFDC export has not completed successfully for more than **2–3 hours**, use the steps below to identify and understand the issue.

1. Go to the **Salesforce Home** page.
2. In the **Quick Find** search box, type **`Bulk Data Load Jobs`** and open it.
3. The page displays bulk data load jobs for the **last 7 days**.
4. Look for jobs related to **Adobe Learning Manager (ALM) objects**.
5. Click the specific job you want to investigate.
6. Scroll to the **bottom** of the job detail page to view the **error message** and additional details.

In many cases, the root cause is **insufficient field-level permissions in SFDC**. The failing field name may look like:

- `cp_Module_ID`
- or other `cp_...` fields related to ALM custom objects.

If such fields appear in the error, proceed to the next section.

## Grant field permissions on ALM custom object fields in SFDC

Use the **Field Accessibility** feature to fix permission issues on specific fields (for example, `cp_Module_ID`).

### Steps

1. Go to the **Salesforce Home** page.
2. In the **Quick Find** search box, type **`Field Accessibility`** and open it.
3. From the list of objects, select the relevant **report type/object**.  
   - Example: `cp_LearnerTranscript_xxxx_xxxx` for the Learner Transcript (LT) report.
4. On the next page, choose **"View by fields"**.
5. In the **field dropdown**, select the field that appeared in the export error  
   - Example: `cp_Module_ID`.
6. In the access matrix, click the **"Hidden"** entry for the **System Administrator** profile (and other relevant profiles, if needed).
7. On the next page:
   - Enable **"Visible"** wherever appropriate.
   - Click **Save** at the bottom of the page.
8. After saving, you return to the field accessibility view. The field should now show as **"Editable"** for **System Administrator** (and any other profiles you updated).

## Repeat for all affected fields and retry the export

1. **Repeat** the field accessibility steps in section 2 for **each field** reported as having permission issues in **Bulk Data Load Jobs**.
2. Once all problematic fields have proper visibility and edit permissions:
   - Go back to **Adobe Learning Manager**.
   - In the **SFDC connector** configuration, **retry the export**.


## Important notes and limitations

Keep these SFDC–ALM specifics in mind when designing or troubleshooting integrations.

### No automatic object/field creation in SFDC

- The **SFDC connector does not create new objects or fields in Salesforce**.
- If a **new field is added in ALM** and you want it to appear in SFDC:
  - Manually **create the corresponding custom field** in SFDC.
  - **Map** the SFDC custom field to the **appropriate ALM field** in the connector configuration.
  - Ensure the new field has **proper field-level permissions** (use section 2).

### Callback URL for ALM accounts with custom domains

- If the ALM account uses a **custom domain**, the engineering team must **add that custom domain** to the **callback URL allowlist** for the SFDC connector's OAuth production app.
- This is done via a **Jira request** to engineering.  
- Without this, the OAuth flow for the connector may fail.

### Time zone limitation (UTC only)

- If the SFDC org uses a **time zone other than UTC**, **completion and enrollment data can be missed** during sync.
- Reason: ALM **currently supports only the UTC time zone** for SFDC integration.
- Internal reference: PAPI-24525 is raised to support additional time zones.

### Filter datatype limitation (picklist vs checklist)

- ALM supports importing **SFDC filters created with picklist fields**.
- ALM **does not support** filters based on checklist/multi-select checkbox fields.
- Reason: ALM **only supports string datatypes** for SFDC filters.
