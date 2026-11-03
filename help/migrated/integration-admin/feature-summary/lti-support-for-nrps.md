---
description: Learn how Adobe Learning Manager uses NRPS to sync custom learner attributes from an LTI 1.3 platform into learner profiles as active fields
jcr-language: en_us
title: LTI support for NRPS
exl-id: 4c972319-b8ce-4f2d-9ccb-1b93c6cc6ac0
---

# LTI support for NRPS

## Overview

Adobe Learning Manager supports the Names and Role Provisioning Services (NRPS) specification when it acts as a Learning Tools Interoperability (LTI) 1.3 tool. When a learner launches Learning Manager from an external learning management system (the platform), Learning Manager retrieves the learner's membership record from the platform. It then copies the custom attributes in that record, such as department or employee ID, into the learner's profile as active fields.

Learning Manager creates learner accounts on the fly when learners launch from a platform through LTI 1.3. Until now, the learner profile was populated only from standard LTI claims, such as name and email address. Platforms often hold richer learner data, such as department, employee ID, or location in NRPS membership records. These attributes aren't part of the standard LTI claims.

With NRPS custom field sync, Learning Manager does the following at launch:

1. Detects that the platform supports NRPS.
2. Requests the launching learner's membership record from the platform.
3. Extracts the custom attributes from that record.
4. Writes the attributes to the learner's profile as active fields. Each field name carries a namespace prefix, so attributes from different platforms don't collide.

Learning Manager reuses the OAuth 2.0 client credentials token that it already uses for Assignment and Grades Services (AGS). You don't need to configure a new token endpoint.

>[!NOTE]
>
>NRPS is an optional specification in LTI Advantage. Support for NRPS and for custom attributes varies by platform. Confirm that your platform exposes NRPS 2.0 before you plan to use this feature.

## Use cases

* **Enrich learner profiles automatically.** Bring attributes such as department, employee ID, or custom metadata from your platform into Learning Manager without manual data entry or separate imports.
* **Analyze where your learners come from.** Capture location attributes, such as country and city, to build a picture of the geographies your learners come from. Use the resulting profile fields for analysis in Learning Manager.
* **Keep profile data aligned with the source platform.** The platform remains the source of truth. Learning Manager refreshes the values each time a learner launches.
* **Support multiple platforms in one account.** Namespace prefixes keep attributes from different platforms separate, even when the platforms use the same attribute name.

## Key features

* **Automatic NRPS detection.** Learning Manager checks every LTI 1.3 launch for the NRPS claim. If the claim is absent, the launch continues normally with no error and no impact to the learner.
* **Launching learner only.** Learning Manager requests only the launching learner's membership record. It doesn't fetch or process the full course roster.
* **Shared token infrastructure.** Learning Manager adds the NRPS scope to its existing AGS token request and reuses the existing per-registration token cache.
* **Namespace-prefixed active fields.** Each custom attribute maps to an active field named `<namespace>_<field_name>`.
* **Automatic field creation.** If no matching active field exists, Learning Manager creates one with the type **Text** and the status **Active**.
* **Platform as source of truth.** Learning Manager overwrites existing profile values with the latest values from the platform. Learners and administrators can't edit these fields.
* **Nonblocking behavior.** NRPS errors never prevent a learner from launching. Learning Manager logs the error and continues.
* **Multiple sources for custom attributes.** Learning Manager can read custom attributes from the NRPS endpoint and from custom parameters in the LTI launch token. Learn more about [custom attributes in the launch token](#custom-attributes-in-the-launch-token).

## Supported configurations

| Item                                                       | Support                                                              |
|----------------------------------------------------------------|--------------------------------------------------------------------------|
| Learning Manager role                                          | LTI 1.3 tool                                                             |
| LTI version                                                    | LTI 1.3                                                                  |
| NRPS service version                                           | 2.0                                                                      |
| Platforms (spec-compliant custom field format)                 | Moodle, D2L Brightspace, Blackboard (Anthology), Sakai                   |
| Custom field serialization pattern (supported in this release) | Pattern S                                                                |
| Platforms planned for a future release                         | Canvas (Instructure): Pattern A. Legacy or unknown platforms: Pattern B. |
| Custom field type                                              | Text                                                                     |
| Trigger                                                        | Each LTI 1.3 launch                                                      |

Platform support depends on the custom-field serialization pattern used in the NRPS member record. Multiple patterns may coexist, but Learning Manager processes only the patterns supported in the active release.

## How it works

### Launch flow

1. A learner launches Learning Manager from the platform.
2. Learning Manager reads the NRPS claim in the LTI 1.3 launch token. If the claim lists NRPS service version 2.0, Learning Manager stores the `context_memberships_url` for the session and for the LTI context (course).
3. Learning Manager requests an access token that includes the NRPS scope `https://purl.imsglobal.org/spec/lti-nrps/scope/contextmembership.readonly`.
4. Learning Manager calls `context_memberships_url?rlid=<lti_user_id>` with the bearer token to retrieve the launching learner's record. If the platform ignores the `rlid` filter and returns the full roster, Learning Manager finds the learner by `user_id`.
5. Learning Manager extracts the custom fields from the record.
6. Learning Manager maps each custom field to an active field and writes the values to the learner's profile.

### Custom field format

The NRPS 2.0 specification defines custom data as a `message` array in the member record. Learning Manager reads the custom data from the LTI custom claim inside that array. For this release, Learning Manager supports the spec-compliant Pattern S representation.

```json
{
  "user_id": "abc123",
  "message": [
    {
      "https://purl.imsglobal.org/spec/lti/claim/custom": {
        "department": "Engineering",
        "employee_id": "E4567"
      }
    }
  ]
}
```

From this record, Learning Manager extracts the following:

| Namespace                                      | Field     | Value   |
|----------------------------------------------------|---------------|-------------|
| `https://purl.imsglobal.org/spec/lti/claim/custom` | `department`  | Engineering |
| `https://purl.imsglobal.org/spec/lti/claim/custom` | `employee_id` | E4567       |

Learning Manager doesn't treat standard NRPS fields as custom fields. The excluded fields are `user_id`, `name`, `given_name`, `family_name`, `middle_name`, `email`, `picture`, `roles`, `status`, and `lis_person_sourcedid`.

### Custom attributes in the launch token

Platforms can also send custom attributes as custom parameters in the LTI launch token. Learning Manager collects attributes from both the launch token and the NRPS endpoint and stores them in the learner profile.

For attributes in the launch token, the custom parameter name must start with the prefix that Learning Manager requires. Without the prefix, Learning Manager can't distinguish these parameters from other custom parameters and doesn't import them. Attributes retrieved from the NRPS endpoint don't need this prefix.

>[!NOTE]
>
>Confirm the exact required prefix with your Learning Manager representative before you configure custom parameters on the platform.

### Active field naming and mapping

Learning Manager builds the active field name as `<namespace>_<field_name>`. For example, the `department` field in the namespace `https://purl.imsglobal.org/spec/lti/claim/custom` becomes `https://purl.imsglobal.org/spec/lti/claim/custom_department`.

Learning Manager applies the following rules:

* **Name length.** If the name exceeds the active field name character limit, Learning Manager shortens the namespace portion first and keeps the field name.
* **Name conflicts.** After shortening, Learning Manager checks for conflicts with existing active fields from a different source. If there is a conflict, it adjusts the shortening length until it finds a unique name. If it can't find a unique name, it skips the field and logs an error.
* **Matching.** Matching of field names isn't case-sensitive.
* **Existing and enabled field.** Learning Manager writes the value to the learner's profile.
* **Existing and disabled field.** Learning Manager skips the field without logging an error.
* **No existing field.** Learning Manager creates a **Text** field with the status **Active**.

### Writing values to the profile

* On each launch where Learning Manager retrieves NRPS data, it writes all resolved custom field values to the launching learner's profile. No other learner profiles are changed.
* If a field already has a value, Learning Manager overwrites it with the latest value from the platform.
* If the platform value is empty or null, Learning Manager keeps the existing profile value.
* A failure to write one field doesn't block the launch or the writes for other fields.
* Learning Manager applies the field updates in the same launch transaction where possible.
* Learners can't edit NRPS-sourced fields on their profile page, and administrators can't edit these values on a learner's behalf.

## Set up NRPS custom field sync

### Prerequisites

* Your platform is registered with Learning Manager as an LTI 1.3 tool. This feature doesn't support LTI 1.1 or LTI 1.2.
* Your platform supports NRPS service version 2.0 and exposes custom attributes in the spec-compliant `message` format.
* The LTI launch token contains the `namesroleservice` claim.
* The claim provides `context_memberships_url`, which identifies the course-specific NRPS endpoint.
* The `service_versions` value in the claim includes `2.0`.
* You have administrator access to the platform's tool registration.

### Grant the NRPS scope to Learning Manager

New registrations that include the NRPS scope work without further changes in Learning Manager. For an existing registration, the platform administrator must update the tool registration on the platform side.

1. On the platform, open the tool registration for Learning Manager.
2. Grant the NRPS scope `https://purl.imsglobal.org/spec/lti-nrps/scope/contextmembership.readonly` to the tool.
3. Save the registration.

>[!NOTE]
>
>You don't need to change the token endpoint, client ID, or private key in Learning Manager. The existing AGS configuration is reused. If the platform doesn't grant the NRPS scope, Learning Manager skips NRPS without affecting AGS or the launch.

### Expose learner attributes on the platform

The platform controls which learner attributes it shares. The exact steps depend on the platform. For example, in Moodle:

1. Add Learning Manager as an external tool using LTI 1.3.
2. Enable the privacy settings that allow the platform to share learner information with the tool.
3. Define the custom attributes that you want to send. You can use platform variables or predefined values.
4. If you also send attributes as custom parameters in the launch token, add the prefix that Learning Manager requires to each parameter name.

>[!NOTE]
>
>Expose only the attributes required for the learning use case. Learning Manager treats the platform as the source of truth and doesn't offer separate consent or privacy controls in this release.

### Verify the sync

1. Launch Learning Manager from the platform as a test learner.
2. Confirm that the launch completes normally.
3. In the Learning Manager admin app, open the active fields page.
4. Confirm that the fields appear with the namespace prefix, with the type **Text** and the status **Active**.
5. Open the test learner's profile and confirm that the values match the platform.
6. Confirm that NRPS-sourced fields are read-only. Neither the learner nor an administrator can manually edit the synchronized values.
7. Relaunch after changing a nonempty source value and verify that Learning Manager overwrites the existing profile value with the latest NRPS value.

>[!TIP]
>
>If a field exists but is disabled, Learning Manager doesn't write to it. Enable the field if you want it populated.

## Use imported attributes for learner grouping

The NRPS-sourced active fields aren't groupable. You can view the synchronized attributes in the learner profile, but you can't use these fields as learner-grouping attributes in this release.

>[!NOTE]
>
>**Release limitation:** Grouping support isn't available for NRPS-sourced active fields. You can't use these fields for learner grouping or segmentation in this release.

## Error handling and logging

Learning Manager never blocks a learner because of an NRPS problem. It doesn't retry. It logs the failure and skips NRPS sync for that launch. The next launch tries again.

| Condition                                                    | Result                                            |
|------------------------------------------------------------------|-------------------------------------------------------|
| NRPS claim is absent from the launch token                       | NRPS is skipped. The launch continues.                |
| Only NRPS service version 1.0 is present                         | NRPS is skipped. The launch continues.                |
| Token request fails or the platform doesn't grant the NRPS scope | NRPS is skipped. AGS and the launch aren't affected.  |
| NRPS call fails (timeout, 4xx, or 5xx)                           | The error is logged. The launch continues.            |
| Learner isn't found in the NRPS response                         | Field sync is skipped. The launch continues.          |
| No custom fields in the NRPS response                            | Field sync is skipped without an error.               |
| A field name conflict can't be resolved                          | The field is skipped and an error is logged.          |
| A single field write fails                                       | Other fields are still written. The launch continues. |

Each log entry includes the timestamp, platform registration ID, learner ID, and failure reason. Learning Manager system administrators can access the logs.

## Limitations

* Only the launching learner's record is synced. Learning Manager doesn't sync the full course roster.
* Only NRPS service version 2.0 is supported.
* All synced fields have the type **Text**. Learning Manager doesn't infer types from values. Number, date, and Boolean field types aren't supported.
* Learning Manager acts as the LTI tool. It doesn't act as an NRPS platform and doesn't provide a roster endpoint to other tools.
* Custom field synchronization occurs during the LTI launch. Real-time synchronization outside the launch isn't supported.
* There's no per-registration administrator toggle for NRPS custom field synchronization.
* Pattern A, used by Canvas, is planned for a future release. Pattern B, for legacy or unknown platforms, is also planned for a future release.

## Troubleshooting

| Symptom                                | Likely cause                                                                                                                                                                  | Action                                                                                                                           |
|--------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| No active fields are created               | The launch token doesn't contain the NRPS claim, NRPS 2.0 isn't advertised, the NRPS scope wasn't granted, the learner wasn't found, or no supported custom fields were returned. | Check the `namesroleservice` claim, `service_versions`, platform-side scope grant, learner membership record, and Pattern S payload. |
| Launch works, but NRPS values don't update | The matching active field is disabled, the incoming value is empty or null, or the field name couldn't be resolved uniquely after truncation.                                     | Enable the matching active field, provide a nonempty source value, and review the system logs for a field conflict.                  |
| NRPS endpoint returns an error             | The endpoint timed out or returned a 4xx or 5xx response.                                                                                                                         | Review the platform registration, bearer token scope, NRPS endpoint, and Learning Manager system logs. The learner launch continues. |
| Token request doesn't grant NRPS access    | The existing LTI registration hasn't been updated to grant the NRPS read-only scope.                                                                                              | Update the platform-side tool registration to grant the required scope. AGS and the launch flow continue independently.              |
| Canvas custom fields aren't imported       | Canvas uses Pattern A.                                                                                                                                                            | Pattern A isn't supported in the current release. It is planned for a future release.                                                |
