---
description: Learn how to configure the interface language with SAML
jcr-language: en_us
title: Set up interface language through SAML
contentowner: chandrum
exl-id: 726cb45e-1c37-42b1-924a-565c84c82852
---
# Set up interface language through SAML

Adobe Learning Manager (ALM) now accepts a SAML attribute for language. This attribute is then mapped to the user's interface and content language settings, ensuring smooth interaction with the LMS in their preferred language. The configuration of these language settings is managed through the Identity and Access Management (IAM) platform, utilizing SAML for Single-Sign-On (SSO). This supports both Service Provider (SP) initiated and Identity Provider (IdP) initiated logins, allowing users to see the interface and content in their chosen language. The workflow is as follows:

1. Create application in Okta
2. Add a user in Okta
3. Configure SSO in ALM

## Create application in Okta

To create an application in Okta, follow these steps:

1. Create a developer account in Okta using your company email and log in to your account.
2. Select **[!UICONTROL Applications]** > **[!UICONTROL Create App Integration]**.
3. Select **[!UICONTROL SAML 2.0]** and then select **[!UICONTROL Next]**.
4. Type a name for the application and select Next.
5. Configure the following fields:

   * **[!UICONTROL Single Sign-On URL]**: Type the specific domain URL to which you want to link the application (for example, [https://learningmanagerstage.adobe.com/saml/SSO](https://learningmanagerstage.adobe.com/saml/SSO)). Change the environment URL if necessary.
   * **[!UICONTROL Audience URI (SP Entity ID)]**: Use the same environment URL as above.
   * **[!UICONTROL Name ID Format]**: Select email address.
   * **[!UICONTROL Application Username]**: Select Okta username.

6. Under Attribute Statements, add the following (or additional fields as needed):
   * **Name**: locale
   * **Name Format**: Undefined
   * **Value**: user.locale

7. Select Next and then select Finish.
8. Once done, scroll down to SAML Signing Certificates:

   * Find the row where the status is **[!UICONTROL Active]**.
   * Select **[!UICONTROL Actions]** > **[!UICONTROL View IdP Metadata]**.
   * This will open an XML file in a new tab. Copy the XML code and save it as a .xml file locally.

## Add a user in Okta

To create a user in Okta, follow these steps:

1. Select **[!UICONTROL Directory]** > **[!UICONTROL People]** and then select **[!UICONTROL Add Person]**.
2. Type the necessary details for the user and select **[!UICONTROL Save]**.
3. Search and select the new user's username.
4. Select **[!UICONTROL Assign Application]**.
5. Select the application you created earlier and then select **[!UICONTROL Save]**.
6. Navigate to the user's profile and select **[!UICONTROL Edit]**.
7. On the locale field, type the required value (for example, fr_FR, en_US) and select **[!UICONTROL Save]**.

## Configure SSO in ALM

To configure the SSO in ALM, follow these steps:

1. Log in as an Admin.
2. Select **[!UICONTROL Settings]** > **[!UICONTROL Login Methods]**.
3. Go to the **[!UICONTROL Single Sign-On (SSO) Configuration]** tab.
4. Select **[!UICONTROL Add new SSO configuration]**.

   ![](assets/sso-add.PNG)
   _Add sso in ALM_

5. Configure the following details and select Save.
   * Type a name for the configuration.
   * Select **[!UICONTROL IDP Initiated ]** from the **[!UICONTROL Single Sign-On (SSO) Settings]** dropdown.
   * For **[!UICONTROL IDP-Initiated Authentication URL]**:

     * Open the metadata XML file you downloaded earlier.
     * Search for the location value and copy it.
     * Paste this value into the IDP-Initiated Authentication URL field.

   * For **[!UICONTROL Metadata XML File]**: Upload the .xml file you downloaded earlier.

6. Go back to the **[!UICONTROL Setup]** tab.
7. From the dropdown, select **[!UICONTROL Single Sign-On Configuration]**.
8. In the **[!UICONTROL SSO Setup]** dropdown, select the configuration name you created earlier.
9. Select **[!UICONTROL Save]**.

## User login and language Setting

When a user logs in using the credentials through SSO, the language attribute passed from the IDP is mapped to the user's interface and content language fields in ALM. The language settings are reflected immediately in the user interface and content without any caching time.

Users can manually update their language settings in the user profile section. These manually updated language preferences will remain in effect and will not be overridden by the IDP settings during future logins.

If a user is soft deleted from ALM, the language settings will be retained in the database. When the same user is added again, the previously set language will be restored. 

Admins can check User Activity, Learning Summary, and Compliance Dashboard reports for language-specific details.

## User language preference update on login through SAML

Adobe Learning Manager is a multilingual platform that supports learners' language preferences in several ways, through the interface, content, and course modules, all available in multiple languages.

With this enhancement, Adobe Learning Manager improves just-in-time user provisioning for native platform users. When new users create accounts and log in for the first time, their language preferences are accurately captured and applied automatically.

### Key Benefits

* Automatically updates users' language preferences during login.
* Provides a personalized experience by displaying the interface and content in the user's preferred language.
* Seamlessly integrates with the SAML authentication process.

When users log in through SAML, their language preference (Interface and Content language) is checked and updated based on the information provided during the login process.

The feature integrates with the SAML login process to capture and update the user's language preference seamlessly. 
