---
title: Safe Exam Browser
description: Enable Safe Exam Browser integration at the account level in Adobe Learning Manager so Authors can require a secure browser environment for native quizzes.
---

# Safe Exam Browser

Safe Exam Browser provides a secure environment for Learners to take native Adobe Learning Manager quizzes by restricting access to other browsers and applications during an assessment.

Administrators can enable Safe Exam Browser integration at the account level and upload a configuration file (.seb) to define quiz restrictions. After the integration is enabled, Authors can configure individual quizzes to require the use of Safe Exam Browser.

This article explains how to enable Safe Exam Browser integration for your account.

## Enable Safe Exam Browser integration

Enable Safe Exam Browser integration to make the option available to Authors when they configure quizzes. Before you begin, ensure that you have the Safe Exam Browser file for your account.

To enable Safe Exam Browser integration:

1. Login to the ALM as an **Administrator**.
1. Select **Settings** > **General**.
1. Navigate to the **Safe Exam Browser integration**.
1. Select **Edit**.

   This expands the **Safe Exam Browser integration**.

1. Select **Enable**.
1. Select **Browse** and upload the Safe Exam Browser file from the system. View [Configure Safe exam browser file](#configure-the-seb-file-for-macos) configuration for more information.

   ![Safe Exam Browser integration settings in General settings](assets/safe-exam-browser-integration-settings.png "Safe Exam Browser integration settings in General settings")

1. Select **Save**.

   The Safe Exam Browser is now available for Authors to enable when configuring supported quizzes.

### Configure the .seb file for macOS {#configure-the-seb-file-for-macos}

Create a .seb file using the SEB Configuration Tool to define your quiz restrictions, security settings, and allowed applications. Before using Safe Exam Browser (SEB), ensure that the .seb file meets the following requirements:

1. Set the browserWindowWebView parameter to 3 (Integer) to enable SEB.
1. Set startURL to the URL that corresponds to the target environment.
1. Ensure that the .seb file includes the required quitURL information.
