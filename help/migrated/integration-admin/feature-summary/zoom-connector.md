---
description: Learn how to integrate Zoom connector with Adobe Learning Manager
jcr-language: en_us
title: Zoom connector
contentowner: mmanuel
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

When creating the app in Zoom, ensure the following scopes are selected:

| Scope Description | Zoom Scope |
|---|---|
| View all user meetings | meeting:read:admin |
| View and manage all user meetings | meeting:write:admin |
| View report data | report:read:admin |
| View all user information | user:read:admin |
| Manage users | user:write:admin |
| Add a meeting registrant | meeting:write:registrant:admin |
| List all meeting registrants | meeting:read:list_registrants:admin |
| Manage sub-account meetings | meeting:write:meeting:master |
| View meeting participants report | report:read:list_meeting_participants:admin |
