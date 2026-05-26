---
description: API changes in ALM
jcr-language: en_us
title: API changes in April release
---

# API changes in the May 2026 release

## GET /learningObjects API enhancement

The GET /learningObjects API now includes a new startDate attribute in the learningObjectInstance resource when the instances relationship is included.

**Endpoint**
GET /learningObjects/{id}?include=instances

**Change**
A new field, startDate, has been added under:
included[].attributes.startDate

**Description**
startDate represents the scheduled start date and time of a learning object instance.

**Example**
https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course:13209797?include=instances
Sample response (truncated)

```
{
  "id": "course:13209797_16226533",
  "type": "learningObjectInstance",
  "attributes": {
    "dateCreated": "2026-05-20T04:35:46.000Z",
    "isAET": false,
    "isDefault": true,
    "isFlexible": false,
    "startDate": "2026-10-06T18:29:59.000Z",
    "state": "Active",
    "timeZoneCode": "IST"
  }
}

```

**Notes**

* The field is returned only for applicable learning object instances.
* The value is returned in ISO 8601 UTC date-time format.
* Existing integrations remain backward compatible.
