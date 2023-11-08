---
jcr-language: en_us
title: Okta Active Directory integration with Adobe Captivate Prime
contentowner: nluke
---


# Okta Active Directory integration with Adobe Captivate Prime {#okta-active-directory-integration-with-adobe-captivate-prime}

In this document, you will learn how to integrate Adobe Captivate Prime with Okta Active Directory (AD).&nbsp;When you integrate Adobe Captivate Prime with Okta AD, you can:

* Check and control Captivate Prime user's access in Okta AD.
* Enable users to be automatically signed in to Adobe Captivate Prime with their Okta AD accounts.&nbsp;
* Manage your accounts in one central location - the Okta portal.

`Adobe Captivate Prime supports Identity Provider (IdP) and Service Provider (SP) initiated SSO.`

## Create an application in OKTA

1. Log in as an Administrator on Okta AD.
1. Click **Applications**. This opens the Application Store in Okta.

   ![](assets/cp-application-store.png)

1. Click **Create App Integration. **&nbsp;

   ![](assets/cp-app-integrations.png)

1. Select&nbsp;**SAML 2.0. **from the new app integration window.&nbsp;

   ![](assets/cp-saml2.0.png)

1. Choose **Create SAML integration** > **General settings page.&nbsp;**Enter an Application Name.

   Note that this can be any name to uniquely identify your application. Once done, click **Next**.

   ![](assets/cp-saml-integration.png)

1. Perform the following steps on the Configure SAML settings page:

   **For IDP setup:**

   1. In the Single Sign-on URL field, type the URL: [https://captivateprime.adobe.com/saml/SSO](https://captivateprime.adobe.com/saml/SSO)
   1. In the Audience URL field, type the URL: [https://captivateprime.adobe.com](https://captivateprime.adobe.com/)
   1. In the **Name ID Format** drop-down box, select **Email Address**.&nbsp;
   
   1. In the **Application username** drop-down, select Okta username.
   1. In case you want to pass any additional attributes, you can add the attributes under the **Attributes Statement** (Optional)

      &nbsp;

   ![](assets/cp-saml-integration-step1.png)

   **For SP setup:**

   1. In the Single Sign-on URL field, type the URL: [https://captivateprime.adobe.com/saml/SSO](https://captivateprime.adobe.com/saml/SSO)
   1. In the Audience URL field, type the URL: [https://captivateprime.adobe.com](https://captivateprime.adobe.com/)
   1. In the Name ID Format drop-down box, select **Email Address**.
   1. In the Application, username drop-down select Okta username.
   1. Click on **Show Advanced Settings**.
   1. Under **Signature Algorithm**, select RSA-SHA256
   1. In the **Assertion Algorithm**, select SHA256
   1. In the **Assertion Encryption** dropbox, select **Encrypted**.
   
   1. In the **Encryption Certificate** option, upload the Certificate file shared by Adobe.
   1. In case you want to pass any additional attributes, you can add the attributes under the **Attributes Statement** (Optional).

   ![](assets/cp-saml-integration-step2.png)

   Once done, click **Next**.

1. The **Feedback **tab is optional. Once you have selected the options and given your feedback, click **Finish.&nbsp;**

   ![](assets/cp-saml-integration-step3.png)

## Extract IDP initiated URL and Metadata file

To&nbsp;view the IdP/SP initiated URL and Metadata file, perform the below steps:

1. Open the application that you have created.
1. Under the&nbsp;**Single Sign-On **tab, click **View Instructions.**

   ![](assets/cp-prime-sso.png)

   **For IDP:&nbsp;**

   1. The Identity Provider Single Sign-On URL is the IdP initiated URL.
   1. Copy all the text that is present under the **Optional **field.&nbsp;
   1. Open a new notepad document and paste the copied text.&nbsp;
   1. Click **File **> **Save as **> “filename**.xml**”. This will be the metadata file.

   **For SP:**

   1. The Identity Provider Single Sign-On URL is the IdP initiated URL.
   1. The Identity Provider Issuer is the Entity ID.
   1. Copy all the text that is present under the **Optional **field.&nbsp;
   1. Open a new notepad document and paste the copied text.&nbsp;
   1. Click **File **> **Save as** > “filename**.xml**”. This will be the metadata file.

   ![](assets/cp-saml-integration-step4.png)

   You need to save this file in an XML format.

## Configuring Adobe Captivate Prime SSO

To configure Adobe Captivate Prime SSO, perform the steps mentioned in the below article.

[https://helpx.adobe.com/in/captivate-prime/kb/sso-authentication-for-captivate-prime.html](https://helpx.adobe.com/in/captivate-prime/kb/sso-authentication-for-captivate-prime.html)
