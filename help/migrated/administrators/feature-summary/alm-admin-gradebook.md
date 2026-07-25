---
description: All about enabling the Gradebook and making it visible to authors and learners
jcr-language: en_us
title: Gradebook for admin
---

# Enable gradebook visibility for your account

## Overview

Before authors can show the gradebook to learners in a course, an administrator must enable the Gradebook visibility setting at the account level. This setting acts as a master switch: when it is off, learners cannot see the gradebook in any course regardless of how individual courses are configured.

## What this setting controls

The **Gradebook visibility** setting in **Settings** > **General** determines whether authors are permitted to expose the gradebook to learners at the course level.

| Setting state | Effect |
| --- | --- |
| Enabled | Authors can control gradebook visibility per course using the **Show gradebook to learners** option in the course editor. Learners see the **Gradebook** tab in courses where the author has enabled it. |
| Disabled | Learners cannot see the gradebook in any course. If it is disabled, the course configuration will not have the setting to show the gradebook to learners. |


This means the account-level setting and the course-level setting work together. Both must be enabled for a learner to see the gradebook.

## Enable gradebook visibility

1. Sign in to Adobe Learning Manager as an administrator.
2. In the left navigation, select **Settings**.
3. Select **General**.
4. Scroll to the **Gradebook visibility** section.
5. Select the **Enable Gradebook view for Learners** checkbox.

    ![](assets/gradebook-admin-1.png)
 
Authors can now configure gradebook visibility per course.

## Impact on author workflows

When this account-level setting is enabled, the **Show gradebook to learners** toggle in the course editor becomes available. Authors use this toggle to decide, per course, whether learners can see the **Gradebook** tab.

When this account-level setting is disabled:

* The **Show gradebook to learners** toggle in the course editor may still appear, but any course-level configuration is overridden. Learners will not see the gradebook.
* Gradebook scores and weighted calculations continue to run in the background for administrator reporting purposes.
* Administrators and custom administrators can still download Learner Transcripts with gradebook data.

>[!NOTE]
>
>Disabling this setting at the account level does not delete any gradebook configurations or scores. If you re-enable it, all previously configured course-level gradebook settings are restored immediately.

## How the two settings interact

| Account-level setting | Course-level setting | What the learner sees |
| --- | --- | --- |
| Enabled | Show gradebook to learners: **On** | **Gradebook** tab visible in the course player |
| Enabled | Show gradebook to learners: **Off** | No Gradebook tab; scores calculated internally only |
