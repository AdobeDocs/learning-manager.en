---
description: Admins can launch an impersonated session where they can log in on behalf of any user in their account in their learner and manager roles.
jcr-language: en_us
title: Impersonation of Learner and Manager
contentowner: saghosh
exl-id: 0306f255-283f-43b9-9494-11b3dc3765da
---
# Impersonation of Learner and Manager {#impersonation-of-learner-and-manager}

In large organizations, customer support personnel need impersonation capability to debug problems faced by learners.

With this ability to impersonate other users, Admins and Custom Admins can identify and perform all the activities done by learners and managers of their organization.

## How it works

Admins (and/or Custom Admins) can search for a user (internal or external) and then impersonate a user. The Admin is then redirected to the user's page (manager app if applicable, or else learner app), and then logs the Admin out of their session. The Admin is then redirected to the Complete your Profile page, in case that is set up for the user who has been impersonated by the Admin.

If a Custom Admin has permission to access a user's page, then they can search for users who they want to impersonate.

Here's what you must keep in mind while impersonating a user:

* All administrators see this feature by default.
* Only active users in the account can be impersonated.
* An Admin cannot impersonate themself.
* A Custom Admin who has access to the Users page can impersonate users.
* An Admin/Custom Admin can only impersonate for 60 mins.
* A Custom Admin with read-only access cannot impersonate users.

## Impersonate a user

To impersonate a user, follow the steps below:

1. Log in to the app as an admin.   
1. Select Profile > Impersonate User. 

   At a time, you can only impersonate one user. 

1. Search for a user (internal/external) in the search box present in the modal. At a time, you can impersonate only one user. Select Proceed. 

   You can also search with user email, UUID, and so on. 

1. A message appears with the confirmation that you will impersonate a user. 

   Select Proceed.

   A confirmation message, "Impersonation Mode: You are logged in as "username (user email). Logout" appears on the header of the page.

**An impersonated session lasts for 60 minutes.**

On changing to a learner or manager role, a message displays indicating that the admin/custom admin is in an impersonation mode of the user. 

## Login and access report

An Admin's login and access are captured in login and access report. For each user who is impersonated by Admin, a record is created in the report.

The columns that are part of this feature are:

* Impersonated by User Name
* Impersonated by User Email

These columns are added at the end of the report.

Each login is counted separately in the report.

## What isn't supported

* Impersonation of AEM Components.
* Impersonation in the mobile app.
* Impersonation in mobile immersive.
* Impersonation of Immersive Apps. It's only applicable to ALM Apps.

## Frequently Asked Questions

+++Can I log in to Adobe Learning Manager even when I am being impersonated?

Yes, a user's login is independent of impersonation.
+++

+++Are impersonation events uniquely counted?

Yes, each login access/visit by admin while impersonation will be counted separately.
+++

+++What is the impersonation timeout?  

It's 60 minutes. If a user who is impersonating closes the browser window and then navigates to any prime URL within 60 minutes, the impersonation activity will be continued, and the banner message must be shown.
+++
