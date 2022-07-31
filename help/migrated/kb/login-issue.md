---
jcr-language: en_us
title: Login issues in Learning Manager
contentowner: nluke
---


# **Issue**

Unable to log in to Adobe Learning Manager.&nbsp;

# **Error**

When trying to log in to Adobe Learning Manager, the error message, shown below, displays:

![](assets/cp-error.png) 

# **Reason**

When a user logs in through SSO, it creates a session cookie that gets stored in the browser. It also enables the user to log in to other applications. Most SSOs are configured to log out after 24 hours. The user has to authenticate again for a new session.&nbsp;

In certain instances, a user is unable to access the system because of stale SSO cookies. These cookies are forwarded to Adobe Learning Manager for authentication. The session does not end if a user does not close the browser for a long time or has not logged out.

Adobe Learning Manager rejects these stale cookies resulting in an error.

# **Resolution**

If a stale cookie gets rejected by Adobe Learning Manager, try the below options:

1. Clear the browser cookies and cache. For more information, see this [document](https://helpx.adobe.com/captivate-prime/user-guide.html/captivate-prime/kb/unable-log-in-captivate-prime.ug.html).  

1.

   Alternatively, the IDP Administrator can define a force logout after a particular set time. This step authenticates the user again to begin a new session.

There are other reasons as to why this error occurs, but the one above is a common scenario.

#### Reference Links:

[https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)
