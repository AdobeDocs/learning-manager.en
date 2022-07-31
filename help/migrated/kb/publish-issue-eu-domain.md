---
jcr-language: en_us
title: Unable to publish to Learning Manager EU domain
contentowner: nluke
---


# Issue

Unable to publish from Adobe Captivate to Adobe Learning Manager EU domain.

# Error

No accounts found

# Description

There are scenarios where authors are trying to publish a course from Adobe Captivate to Adobe Learning Manager. However, they are unable to do so as they see an error message, "No account found".

# Cause

This issue occurs because Adobe Captivate is by default configured to publish content to the US domain of Adobe Learning Manager.

# Resolution:

#### Things to note:

* If open, close the Adobe Captivate application.
* You would require Administrator access on your machine to perform the below steps. In case you do not have Admin access, please reach out to your IT team for assistance.

#### Perform the below steps:

1. Go to the installation directory for Adobe Captivate.&nbsp;

   For example,  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64` (2019 is the Captivate version. Differs if you are using a different version of Adobe Captivate).

1. Copy the configuration file **AdobeCaptivate.ini** to your desktop.

   ![](assets/cp-captivate.ini.png)

1. Open the copied file from your desktop onto a Notepad.
1. Change the value of PrimeBaseUrl = [https://captivateprime.adobe.com/inappstarter](https://captivateprime.adobe.com/inappstarter)&nbsp;to PrimeBaseUrl = [https://captivateprimeeu.adobe.com/inappstarter](https://captivateprimeeu.adobe.com/inappstarter)

   ![](assets/cp-primebaseurl.png)

1. Save changes made to the Notepad.
1. Copy the saved file that you edited and paste it back to the file path. Replace the original file in  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64`
1. Once done, launch Adobe Captivate and try publishing to Adobe Learning Manager.

