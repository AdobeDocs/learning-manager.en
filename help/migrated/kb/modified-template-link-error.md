---
jcr-language: en_us
title: Email links triggered from modified templates throw an error in Learning Manager
description: Email links triggered from modified templates throw an error in Adobe Learning Manager
contentowner: nluke
preview: true
---


# Email links triggered from modified templates throw an error in Learning Manager {#email-links-triggered-from-modified-templates-throw-an-error-in-learning-manager}

## Issue

An error occurs after clicking a link for an automated email/welcome email/enrollment mail.

**Error**

HTTP Status 400 - Bad request

![](assets/email-404.png) 

## Cause

This usually happens when the email templates are incorrectly customized.

**Solution**

To avoid any errors that are related to broken links, which may appear due to customization, follow the steps below:

1. Log in as an Administrator.
1. In the left panel, click **Email Templates.** 

1. Navigate to the required template and click to modify it.

   This opens the **Template preview** window.

   ![](assets/email-template.png)

   Note the points when editing an email template:

   * We recommend that you modify an email template from within the Learning Manager interface.
   * Copy-paste the modified template on to a Notepad/Word file to store a copy of the changes made.
   * Avoid replacing any dynamic text in the template which is highlighted in blue. For example, "**OrganizationName**", "**Learner**", "**click here**", "**CertificateName**", and so on.

1. Click **Save** to confirm the changes applied to the template. 
1. Trigger the email to verify if the links work as expected.
1. Revert the settings to original by clicking the option **Revert to Original** for the modified template.
