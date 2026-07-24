---
description: The Incremental User Report Job API lets administrators export only users whose data changed within a specified date range. This eliminates the need for full user exports and enables more efficient synchronization of new or updated user records.
jcr-language: en_us
title: Incremental User Report (Job API)
---

# Incremental User Report (Job API)

## Overview

Adobe Learning Manager's Incremental User Report is a new Job API feature that lets administrators and integration developers export only the users whose data has changed within a specified date-and-time window. Instead of pulling the complete user list every time, you can request a targeted slice covering only new or modified users.

This document covers:

- Why incremental reporting exists and when to use it
- How the feature works – including the change-tracking model
- The new Job API for incremental user reports (payload, parameters, pagination)
- How to handle large accounts (5,00,000+ users)
- Tracked vs. non-tracked fields
- Limitations and non-goals

## Why use Incremental Reporting

This section explains the motivation for the feature and should help you decide whether incremental or full exports best fit your integration.

## The problem with Full User Exports

The current full user export (generateUsers job type) returns every user in an account with every execution. For large enterprise accounts this creates two significant problems:

| Customer | User Volume |
|----------|-------------|
| Customer A | 2.1 million users |
| Customer B | 7 million users |
| Customer C | 1 million+ users |
| Customer D | 7.7 million users (migration) |


* At these scales the export pipeline runs at approximately 90% CPU utilization while fetching, processing, and storing data.
* Downstream dashboards (PowerBI, Salesforce, custom integrations) re-ingest unchanged user records on every run, wasting bandwidth and processing time.
* There is no way to ask "which users changed since my last export?" using the current API.

## When to Use Incremental Reporting

Use the incremental export when you need to keep an external system synchronized with Adobe Learning Manager user data. Typical use cases:

* Keeping an enterprise dashboard (PowerBI, Tableau, SFDC) up to date with user profile changes.
* Feeding downstream identity management systems with role, state, or metadata changes.
* Running nightly or hourly delta-sync pipelines instead of full reloads.
* Reducing API load and data-transfer costs for accounts with millions of users.

Use the full export (generateUsers) when you need an authoritative baseline – for example, on first setup or after a long gap between syncs.

| Export Mode | Use when… |
|-------------|-----------|
| Full export (generateUsers) | Initial bootstrap; accounts with fewer than 50k users; recovery after a missed sync window. |
| Incremental export (generateUserIncrementalReport) | Regular delta-sync; large accounts; pipelines that need only changed records |

## Current Full User Report

(generateUsers) This section documents the existing Job API user report for reference. If you are already familiar with it, skip to the next section.

## How It Works

The current user CSV report is submitted as a job via the Jobs API. A Snaplogic pipeline picks up the task, executes a MySQL query against the CAPTIVATE database (user, usergroup, usergroup_user tables), and generates a CSV file.

## Available Filters

The payload supports three optional filters:

* `expandMetadata` – Pass true to export metadata as a separate column.
* `fetchActiveUsers` – Pass true to export only active users.
* `peerAccountId` – To generate the user report for a peer account.

## CSV Columns

The exported CSV contains the following columns:

```
internalUserID, userEmail, customerDefinedUniqueUserId, name, managerEmail,

userType, state, excludedFromGamification, pointsEarned, profile, roles,

dateCreated, lastLoginDate, dateDeleted, uiLocale, contentLocale,

timeZoneCode, userSource, group, AF_location, AF_login, AF_externalaf,

lastSocialActivityDate

```

## Request Payload

Job type: generateUsers. Admin role only.

```
{

  "data": {

    "type": "job",

    "attributes": {

      "description": "<description of your choice>",

      "jobType": "generateUsers",

      "payload": {

        "expandMetadata": "<true to export metadata as separate column>",

        "fetchActiveUsers": "<true to export ACTIVE users only>",

        "peerAccountId": "<peerAccountId for peer account report>"

      }

    }

  }

}
```

## Limitations

* No date-based filtering – every execution exports all users.
* Not feasible for large accounts – pipeline resource exhaustion above ~1 million users.
* No incremental or delta capability.

## Incremental User Report (generateUserIncrementalReport)

This section documents the new incremental user report feature introduced in M46. This is the primary subject of this document.

## What Is an Incremental Export?

An incremental export returns only users whose tracked data has changed within a specified start and end date-time window. The backend stores a last-modified timestamp for each user's tracked fields. When you request a report for a given window, only users whose most recent change falls within that window are included.

## How the Change-Tracking Model Works

Adobe Learning Manager maintains a last-modified timestamp that is updated whenever any tracked field for a user changes. 

When you request an incremental report with a start_date_time and end_date_time, the system returns users whose last-modified timestamp falls within [start_date_time, end_date_time]. If a user was modified both within and after the window (i.e., they were changed again after end_date_time), that user is not included in the report – because their last-modified timestamp is now beyond the window.

>[!NOTE]
>
>This means an incremental export captures users whose most recent change is in the specified window – not every user who was touched at any point during the window.

## Fields tracked for changes

A user is included in an incremental report if any of the following fields changed:

| Field | Notes |
|---|---|
| userEmail | Email address of the user |
| name | First name of the user |
| managerId | User table stores managerId. If the managerId changes, the field is flagged as changed. If only the manager's email changes (same managerId), this field is NOT considered changed. |
| type | Internal or external user classification |
| state | Active or deleted |
| profile | User profile assignment |
| roles | Role additions or deletions |
| uiLocale | User interface locale |
| contentLocale | Content locale |
| timeZoneCode | User time zone |
| Active Fields (AF_*) | All configured active fields, e.g. AF_location, AF_login |
| metadata | All configured metadata fields |

## Fields NOT Tracked for Changes

The following fields appear in the CSV output but do not trigger inclusion in an incremental export when they change:

* excludedFromGamification
* pointsEarned
* lastLoginDate
* dateDeleted
* dateCreated
* userSource
* lastSocialActivityDate

## Output Format

The incremental CSV report has the same columns and format as the full user CSV report. All columns appear in the same order, including all active field and metadata columns – regardless of which fields changed for the exported users.

>[!NOTE]
>
>If a new active field is added or an existing one is removed, all users affected by that change will appear in the next incremental export. New columns from new active fields are appended at the end of the report so that existing integrations keyed on column position do not break.

## New Job API for Incremental User Report

The incremental user report uses the Job API to generate a CSV file that contains users whose tracked data changed within the specified date-and-time window. For large result sets, use the same pagination model described later in this document: submit the same date window in each request and pass the last userId received in the previous response as fromUserId to retrieve the next chunk.

## Job Type

Job type: generateUserIncrementalReport

## Request Payload

```
{

    "data": {

        "type": "job",

        "attributes": {

            "description": "description of your choice",

            "jobType": "generateUserIncrementalReport",

            "payload":{

                 "fullExport": <Pass true to export all users. If fullExport is true, fromDate and toDate are ignored>,

                 "expandMetadata": <Pass true to export metadata as separate columns>,

                 "fromDate": <Start of the change window in ISO format, for example 2020-01-01T18:30:00.000Z>,

                 "toDate": <End of the change window in ISO format, for example 2020-01-31T18:30:00.000Z>,

                 "fromUserId": <For paginated requests, pass the last userId received in the previous response>

            }

        }

   }

}
```

## Payload Parameters

| Parameter | Type | Description |
|---|---|---|
| fromDate | String (ISO 8601) | Required for incremental export. Start of the change window. Use ISO 8601 format. |
| toDate | String (ISO 8601) | Required for incremental export. End of the change window. Use ISO 8601 format. |
| fromUserId | String | Optional. For paginated requests, pass the last userId received in the previous response as fromUserId. Omit this parameter for the first request. |
| expandMetadata | Boolean | Optional. If true, exports metadata as separate columns. |

For incremental export, pass `fromDate` and `toDate` to define the change window. If the result set is larger than one chunk, continue pagination by sending the same `fromDate` and `toDate` and passing the last `userId` from the previous response as `fromUserId`. If fullExport is true, the date window is ignored and the API generates a full user export.

## Handling Large Accounts (500k+ Users)

User reports are generated using a data platform pipeline and output is returned in chunks to support large accounts. If an incremental export covers more than 500,000 users, the report is paginated.

## Pagination Model

To retrieve all pages for a large incremental export, pass the same startDateTime and endDateTime in each request, and additionally pass the userId of the last user received in the previous chunk as fromUserId. The API will return the next set of up to 500,000 users with userId greater than the passed fromUserId.

## Pagination Workflow

Step 1: Submit the first request without fromUserId.

```
// First request – no fromUserId

{

  "payload": {

    "startDateTime": "2026-05-01T00:00:00Z",

    "endDateTime": "2026-05-31T23:59:59Z"

  }

}
```

Step 2: Receive the first chunk (up to 500,000 users). Note the last userId in the response.

Step 3: Submit the next request, passing the same date window and the last userId from the previous response as fromUserId.

```
// Subsequent request – pass last userId from previous response as fromUserId

{

  "payload": {

    "startDateTime": "2026-05-01T00:00:00Z",

    "endDateTime": "2026-05-31T23:59:59Z",

    "fromUserId": "<last userId from previous response>"

  }

}
```

Step 4: Repeat until a response returns fewer than 500,000 records, indicating you have reached the last page.

| Request | fromUserId Parameter |
|---|---|
| First page | Omit fromUserId |
| Second page | Pass the last userId from the first page as fromUserId |
| Third page | Pass the last userId from the second page as fromUserId |
| … (continue) | … |
| Last page | Response contains fewer than 500,000 records |

>[!NOTE]
>
>Ensure your `startDateTime` and `endDateTime` remain identical across all paginated requests for a single export run. Changing the date window mid-pagination will produce inconsistent results.

## Limitations

The incremental user report is intentionally scoped. The following capabilities are out of scope:

* Not a user audit report – it does not list which specific fields changed.
* No old/new value comparison – the report shows current field values only.
* No per-change timestamps – the time of individual field modifications is not surfaced.
* No indication of the number of changes – a user modified once and a user modified ten times appear identically in the export.
* Existing report format is unchanged – the CSV column structure is the same as the full user report.

## Connector integration

The incremental user report is designed to be used in Adobe Learning Manager connectors (PowerBI, Salesforce, and others) as a drop-in replacement for the full user report in regular sync pipelines. This allows connectors that today use generateUsers to migrate to the incremental model without changes to the downstream data schema.

* The output CSV is column-compatible with the full user report.
* Connectors can use the incremental report for delta-sync and fall back to the full report for bootstrap or recovery.
* Support for connector integration (PowerBI, SFDC) 
