---
jcr-language: en_us
title: Unable to publish to Learning Manager EU domain
description: Unable to publish from Adobe Captivate to Adobe Learning Manager EU domain in Adobe Learning Manager.
contentowner: nluke
exl-id: fb8ae1af-9902-4901-8263-fb3ebff98fbc
---
# Unable to publish to Learning Manager EU domain {#unable-to-publish-to-learning-manager-eu-domain}

## Issue

Unable to publish from Adobe Captivate to Adobe Learning Manager EU domain.

## Error

No accounts found

## Description

There are scenarios where authors are trying to publish a course from Adobe Captivate to Adobe Learning Manager. However, they are unable to do so as they see an error message, "No account found".

## Cause

This issue occurs because Adobe Captivate is by default configured to publish content to the US domain of Adobe Learning Manager.

## Resolution:

Things to note:

* If open, close the Adobe Captivate application.
* You would require Administrator access on your machine to perform the below steps. In case you do not have Admin access, please reach out to your IT team for assistance.

Perform the below steps:

1. Go to the installation directory for Adobe Captivate. 

   For example,  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64` (2019 is the Captivate version. Differs if you are using a different version of Adobe Captivate).

1. Copy the configuration file **AdobeCaptivate.ini** to your desktop.

   ![](assets/cp-captivate.ini.png)
   *View the configuration file*

1. Open the copied file from your desktop onto a Notepad.
1. Change the value of LearningManagerBaseUrl = `https://learningmanager.adobe.com/inappstarter` to LearningManagerBaseUrl = `https://learningmanagereu.adobe.com/inappstarter`

   ![](assets/cp-primebaseurl.png)
   *View PrimeBaseURL*

1. Save changes made to the Notepad.
1. Copy the saved file that you edited and paste it back to the file path. Replace the original file in  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64`
1. Once done, launch Adobe Captivate and try publishing to Adobe Learning Manager.
