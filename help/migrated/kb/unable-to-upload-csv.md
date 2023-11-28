---
description: When uploading a CSV, an error appears. Read on to resolve the issue.
jcr-language: en_us
title: Unable to upload CSV
contentowner: saghosh
---


# Unable to upload CSV

## Error: Data truncation: Data too long for column

When trying to upload a CSV in Adobe Learning Manager, you see the following error message.

![](assets/csv-upload-failed.png)

## Cause

The error happens if the data present in the specified column exceeds the character limit that is defined for the column.

## Resolution

* Open the CSV.
* Check the data in the column that is mentioned in the error.
* If there is any value that is large (for example, greater than 60 characters), change the value to correct the data.

## Error: First column in the CSV displays a special character

You are unable to upload a CSV because the first column displays a special character when mapping the columns.

![](assets/csv-2.png)

## Cause

The issue occurs when the CSV is saved as a UTF-8 format in Excel. When you save a CSV in Excel as UTF-8, the file is saved in a UTF-BOM format. You can either verify this using Notepad++ or when you upload a CSV to Learning Manager, while mapping the columns, the first column displays a special character.

## Resolution

* **A:** Saving via Excel:

   1. Open the CSV in Excel.
   1. Save the file as a normal CSV.

* **B:** Saving via Notepad or Notepad++:

   * Open the CSV in Notepad or Notepad++.
   * Save the file in a UTF-8 format.

## Error: Email address of user already present in the system

You are unable to upload a CSV because CSV processing has failed. You see the error message below:

![](assets/csv-3.png)

## Cause

This issue occurs if there is a user who is already present in the system with the same email address or UUID.

## Resolution

### Scenario 1

**Accounts on which UUID is not enabled.**

In this scenario, there are two reasons for this error:

1. The user that you are trying to add is a Manager of an External profile. To resolve this, open the external profile the user is a part of, select the user, click **Actions** > **Assign Role** > **Manager**, and change the Manager of the profile.
1. The user that you are trying to add has been purged. In this scenario, you will not be able to add the user with the same email address until the purge process is completed. As a workaround**, a**dd the user with a secondary email address to provide access to the platform. Once the purge process is complete, edit the user and change the email address to the correct email address.

### Scenario 2

**UUID-enabled accounts.**

For UUID-enabled accounts, this issue can occur if a user has been assigned a UUID that is already being used by another user on the account or if the user has a different email address.

For example, let there be two users, A and B, with email addresses,  a@xyz.com and b@xyz.com with UUID 1 and 2 respectively.

Now, if you upload a CSV that has user A's UUID as 3 and user B's UUID as 2, then you will see an error.

To resolve this issue, **you must have the same email address and UUID for the user on the CSV and the system.**
