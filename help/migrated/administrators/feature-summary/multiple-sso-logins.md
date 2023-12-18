---
description: Adobe Learning Manager supports multiple login methods through multiple SSO configurations for both internal and external users.
title: Multiple SSO logins
contentowner: saghosh
---

# Multiple SSO logins {#multiple-sso-logins}

An Administrator can configure multiple login methods for both internal and external users. Adobe Learning Manager supports multiple SSO logins that will help admins to configure the login method based on their needs and use cases.

The intent is to allow admins to configure different SSO for different user groups based on their location, organization, etc.

Up to 20 SSO configurations can be added to an account. These can be used to set up SSO for both internal and external users.

>[!NOTE]
>
>On enabling Multi-SSO, you can choose values or user groups at the self-registration profile. On choosing a value, a user group with zero users gets created. Such a user group do not have any user. When the next CSV gets imported, this user group will be removed.

## Enable multiple SSO

To enable multiple SSO, select **Settings** > **Login Methods**.

On the setup page, select the checkbox 'Enable Multiple Single Sign-On (SSO)' for Internal or External users.

When Multi SSO is enabled, the login method selected for 'Default Login Method' becomes the default login type for user groups/profiles that are not linked to any SSO configuration. The default login can be Adobe ID or SSO or ALM ID (External users).

To configure an SSO, follow the steps below: 

1. Click Configure Single Sign-On (SSO).   
1. Click Add new SSO configuration.   
1. In the SSO Configuration dialog, add the following:

   * Enter the name of the SSO.
   * Select the type of SSO- IDP initiated, or SP initiated.

      * If you've selected IDP initiated, then enter the IDP URL. This will be the URL that will be the unique identifier for your application and is information that is provided by your IDP service provider. This is the URL all Adobe Learning Manager users will be redirected to after logging in.  
      * Upload the IDP Metadata XML from your IDP provider. This file contains information about the IdP that enables Adobe Learning Manager to accept SAML assertions from it
      * If you've selected SP initiated, enter the Entity ID. The Entity ID is a URL that the Service Provider (SP) provides.
      * Enter the SP Login URL. This URL is used by the users to log in to the application.

1. The SSO configuration gets added to the list. 

## Set up SSO for internal users

### Users from a CSV

Follow the steps below:

1. Import the CSV that contains the active fields and their values.  
1. Click Settings > Login Methods.  
1. Enable the Enable Multiple Single Sign-On (SSO) for login checkbox.  
1. Map the SSO configurations to the values of the active field.  
1. Save the settings. Import the CSV again.

### Single user

Follow the steps below:

1. Click Settings > Login Methods.   
1. Enable the Enable Multiple Single Sign-On (SSO) for login checkbox.   
1. Select an active field for an SSO.   
1. Link the SSO configurations to the values of the field.   
1. Save the settings. Add a single user and assign a value for the active field.

### Self-registered users

Follow the steps below:

1. Click Settings > Login Methods.   
1. Enable the Enable Multiple Single Sign-On (SSO) for login checkbox.   
1. Link the SSO configurations to the values of the field.   
1. Save the settings. Add a single user and assign a value for the active field.  
1. Add a self-registration profile.   
1. Select a value for the SSO field configured.

After saving the profile settings,  the copied URL redirects the users to the SSO linked to the value chosen for the profile.

### Set up SSO for external users

Follow the steps below:

1. Create an external profile.  
1. Click Settings > Login Methods.  
1. Enable the Enable Multiple Single Sign-On (SSO) for login checkbox.  
1. Link the SSO configuration to the external profile created.  
1. Save the settings.

After saving the profile settings, Once saved, the External profile URL copied will redirect the users to the SSO linked to the profile.

## Frequently Asked Questions

+++ Who can enable multiple SSOs for users?

Both the Administrator and the Custom Administrator can enable multiple SSOs.
+++

+++Can I use an existing or a new single-valued active field?

Yes, you can use an existing or a new single valued active field to set up multiple SSOs.
+++

+++If there are disabled fields in a CSV, will the setting up of multiple SSOs fail?

No, it will not affect setting up the SSOs. Users will be redirected to an already configured SSO.
+++

+++Can an Admin add new values to the active field on the page while setting up Multi-SSO?

Yes, an Admin can add new values to the active fields.
+++

+++Can I disable or delete fields linked to SSO?

Yes, you can disable or delete fields linked to SSO until you unlink the fields from the SSO setup page.
+++
