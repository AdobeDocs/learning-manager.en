---
jcr-language: en_us
title: Social login in Learning Manager
contentowner: saghosh
preview: true
---


# Social login in Learning Manager {#social-login-in-learning-manager}

# Set up Social Login {#setupsociallogin}

You can use your Facebook, LinkedIn, or Twitter credentials to log in to Learning Manager.

1. Reach out to your Customer Success Manager, if you'd like him/her to set up the account.

   Otherwise, follow the steps below.

1. Search for the account where you'd like to set up social login.
1. Change the login to SSO.
1. Click Advanced. Specify the following JSON.

   ```
   \{"linkedIn":true,"microsoft":true,"twitter":true,"facebook":true,"editingAllowed":true
   ```

   If it is an incorrect JSON, there will be an exception.

   This social login feature is only used for INTERNAL users.

