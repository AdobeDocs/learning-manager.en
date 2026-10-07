---
description: Learn how to integrate Zoom connector with Adobe Learning Manager
jcr-language: en_us
title: Zoom connector
contentowner: mmanuel
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
---

# Zoom connector in Adobe Learning Manager

## Introduction

The Zoom Connector in Adobe Learning Manager allows seamless integration with Zoom to deliver live virtual classroom sessions. With this integration, instructors can host Zoom meetings directly from Learning Manager, enroll learners, and track attendance and completion data. Learners receive automatic invites and can join sessions through their Adobe Learning Manager accounts. After the session, attendance and performance data are synced back to Adobe Learning Manager for reporting and tracking.

## Set up the Zoom connector

To configure the Zoom Connector:

1. Log in to Adobe Learning Manager as an integration administrator.
2. Hover over the **Zoom** tile.

    ![](assets/zoom-connector1.png)
    _Configure Zoom Connector in Adobe Learning Manager_

3. Select **Connect**. The Zoom connector setup page opens.
4. Type the following account details in the respective fields. You can get these credentials from your Zoom account administrator:

    * Connection Name
    * Zoom Account ID
    * Client Id
    * Client Secret
    * Super Admin Email address

    ![](assets/zoom-connector2.png)
    _Type the configuration details to set up the Zoom connector_
    
5. Select **Connect** to establish the integration.

>[!NOTE]
>
>When enabling the connector, **learners must use the same email address** for both their Zoom and Adobe Learning Manager accounts to ensure user data syncs correctly.

## Create Zoom courses

Once the connection is established:

1. Log in as an **Author** and create a new Virtual Classroom course.
2. Select **Zoom** as the conferencing system during course creation.
3. Assign learners to the course via administrators, managers, or through self-enrollment.
4. Upon enrollment, learners receive an email with course details.
5. Learners can log in to their Adobe Learning Manager account to access the course and join the Zoom session.

## Track attendance and completion

After the virtual session ends:

* Adobe Learning Manager automatically receives the completion status from Zoom.
* Administrators can view attendance and scoring reports in Adobe Learning Manager to track learner participation and performance.

## Create a Zoom server-to-server OAuth app

To use the Zoom Connector with Adobe Learning Manager, you must create a Zoom Server-to-Server OAuth app and configure the required scopes.

### Required OAuth scopes

When creating the application in Zoom, ensure the following scopes are selected:

| What you want | Search this keyword | Then pick |
|---|---|---|
| View all user meetings | meeting | `meeting:read:meeting:admin, meeting:read:list_meetings:admin` |
| View/manage all user meetings | meeting | `meeting:update:meeting:admin, meeting:delete:meeting:admin, meeting:write:meeting:admin` |
| View report data | report | `report:read:meeting:admin, report:read:user:admin` (Pick the one matching your endpoint.) |
| View all user information | user | `user:read:user:admin, user:read:list_users:admin` |
| Manage users | user | `user:update:user:admin, user:write:user:admin` |
| Add a meeting registrant | registrant | `meeting:write:registrant:admin` |
| List all meeting registrants | registrant | `meeting:read:list_registrants:admin` |
| Sub-account meetings | meeting + look for :master | `meeting:write:meeting:master` |
| Meeting participants report | participant | `report:read:list_meeting_participants:admin` |

