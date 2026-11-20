---
description: Learn how Adobe Learning Manager marks learners as attended when they watch an Adobe Connect session recording, with no manual updates
jcr-language: en_us
title: Track attendance through Adobe Connect recording views
exl-id: f4cb951e-3cb1-4caf-b6b8-aec86b32f782
---

# Track attendance through Adobe Connect recording views

## Overview

Adobe Learning Manager can track attendance for Adobe Connect virtual classroom sessions through recording views. When a learner misses a live session but watches the recording on Adobe Connect for long enough, Learning Manager marks the learner as having attended the session. The learner then completes the session module and can move toward completing the learning object that the session belongs to.

Before this feature, Learning Manager had no way to record attendance for learners who watched a Connect recording. A learner who missed a live session couldn't complete it, and an instructor had to step in and mark attendance manually. This feature removes that manual step. Adobe Connect reports who watched which recording and for how long, and Learning Manager compares the watch time with the completion criteria set for the account.

Once the learner meets the completion criteria for the recorded session ,learners are marked in the Admin app.

The Learner's email ID should be the same in Adobe Learning Manager and Adobe Connect since Adobe Learning Manager redirects the Learner to Adobe Connect using the same email ID.
The default sync frequency and the shortest interval the Integration Admin can set is one hour.


## Who does what

| Role                   | What they do                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Learner                    | Opens the session recording and watches it after missing the live session.                                            |
| Instructor                 | Starts the recording during the live session, so a recording and transcript exist.                                    |
| Integration Admin          | Configures the Adobe Connect account that the attendance sync uses, and sets the sync schedule or turns it on or off. |
| Author or delivery manager | Schedules the virtual classroom sessions and, for multiday programs, reuses a persistent room across days.            |
| Adobe Connect              | Captures each learner's email and recording watch time, and exposes the list of recording viewers through an API.     |

Each role has a separate part in making recording-based attendance work.

## Glossary

| Term                        | Meaning                                                                                            |
|---------------------------------|--------------------------------------------------------------------------------------------------------|
| Virtual classroom session       | A virtual classroom session hosted on Adobe Connect.                                                   |
| Virtual instructor-led training | Training that an instructor delivers through virtual classroom sessions.                               |
| Learning object                 | A course, for example, that contains the session module.                                               |
| Persistent room                 | An Adobe Connect room that can be reused for several sessions, for example on day 1, day 2, and day 3. |
| Completion criteria             | The percentage of the recording a learner must watch to be marked complete for the module.             |

## Use cases

### A learner misses a live session

A learner can't join the live virtual classroom session. Later, the learner opens the session in Learning Manager and watches the recording. Once the watch time meets the completion criteria, Learning Manager marks the learner as attended and the learner completes the module without asking the instructor for help.

### A learner who only partly watches

A learner opens the recording but watches less than the required share. The completion criteria aren't met, so Learning Manager doesn't mark the learner as attended.

### Multiday sessions on one persistent room

An author or delivery manager schedules sessions for day 1, day 2, and day 3 on the same persistent Connect room. They can see and reuse the room name without signing in to Adobe Connect.

## Key features

| Feature                   | What it does                                                                                                              |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Automatic attendance          | Marks a learner as attended for a Connect-based virtual classroom session when the learner watches the recording long enough to meet the prescribed threshold limit. |
| Watch time from Connect       | Uses the learner email and recording watch time that Adobe Connect captures.                                                  |
| Completion criteria threshold | Marks the learner complete for the module when watch time reaches the percentage set in the completion criteria.              |
| Actual watch time only        | Counts the time a learner really watched. Dragging the seek bar doesn't add watch time.                                       |
| Scheduled sync                | Runs a back-end pipeline on a schedule that the Integration Admin controls, and can be turned on or off.                      |
| Persistent room visibility    | Shows the Connect room name at instance level so authors can reuse a persistent room across days.                             |

## How attendance tracking works

*From a learner opening the recording to Learning Manager marking the module complete.*

### End-to-end flow

1. The instructor hosts the live virtual classroom session on Adobe Connect and starts the recording. The recording and transcript become available after the session.

1. A learner who missed the session selects the recording to view it. Adobe Connect tracks the view automatically.

1. Adobe Connect captures the learner's email and the time the learner actually spent watching.

1. On the configured schedule, a back-end SnapLogic pipeline calls the Adobe Connect API and pulls the list of recording viewers for a given time frame. The pipeline uses the Adobe Connect account set up in Integration Admin.

1. Learning Manager maps each viewer to the matching course and module.

1. Learning Manager compares the learner's total watch time with the completion criteria.

1. If the watch time meets the criteria, Learning Manager marks the learner complete for the module. In the back end, Learning Manager records this by populating the user course grade CSV.

>[!NOTE]
>
>Adobe Connect doesn't push data to Learning Manager. Learning Manager pulls it at the Adobe Connect instance level, for example "these five users watched these six recordings in the last 24 hours." Attendance therefore updates after the next pipeline run, not the moment the learner finishes watching.

### Completion criteria and watch time

The learner must watch at least the percentage of the recording that the completion criteria define. Keep these rules in mind:

* The percentage applies to the recording duration, not the scheduled session duration. If a 15-minute session is recorded for only 5 minutes, the required time is based on the 5 minutes. Adobe Connect supplies the recording duration.

* The percentage is set on the Learning Manager side. It's a common setting across the account, not a setting for each instance. The same type of setting already applied to live sessions, for example requiring 80% participation.

* Adobe Connect records how long the learner really watched. Jumping ahead with the seek bar doesn't count, and Learning Manager processes the watch time that Connect passes.

| Completion criteria | Recording length               | Watch time needed | Result                                                  |
|-------------------------|------------------------------------|-----------------------|-------------------------------------------------------------|
| 50%                     | 5 minutes                          | 2.5 minutes           | Marked complete once 2.5 minutes are watched.               |
| 50%                     | 5 minutes (session was 15 minutes) | 2.5 minutes           | Based on the 5-minute recording, not the 15-minute session. |
| 0%                      | Any                                | None beyond opening   | Opening the recording is enough.                            |

### Eligibility window

Learning Manager applies recording-based attendance only up to the completion date of the learning object. If the learning object has no completion date, Learning Manager uses the completion date of the parent learning object.

### Schedule the sync

The Integration Admin controls how often the pipeline runs. The schedule can be hourly or weekly, among other intervals, and the Integration Admin can turn the schedule on or off. The same Adobe Connect account is used for every run.

### What changes

* When a user adds the persistent room created for day 1, Learning Manager gives them access to that room. They can then add the same room to sessions on other days.
* Learning Manager shows the Connect room name at instance level, in the session details next to the **Virtual Classroom URL**.
* For the default instance, Learning Manager shows the room set up during course creation.

### Limitations and considerations

* Attendance isn't real time, because Learning Manager pulls data on a schedule.
* The feature covers Connect-based virtual classroom sessions only.
* A recording must exist, so the instructor must start the recording during the live session.
* Learners are matched through the email address that Adobe Connect captures.
* Dragging the seek bar doesn't add watch time.
* Recording-based attendance stops at the completion date of the learning object, or of the parent learning object.

### Points to remember

* Watch time must be greater than or equal to the percentage prescribed (for example 50% of 5 minutes is 2.5 minutes). Watch time does not add up if the Learner repeatedly watches the session but is still short of the prescribed watch time. However, watch time adds up even if the Learner watches the session at different points of time in parts and meets the threshold criteria. For example, if a Learner watches one minute of the session on day 1 and then watches another 1.5 minutes of the session the next day from the point where he left, the watch time adds up. This happens on the Adobe Connect side.

* Completion criteria can be configured at course level and account level. The effect is the same as the live session participation.

* The default sync frequency and the shortest interval the Integration Admin can set is one hour.

* The Learner's email ID should be the same in Adobe Learning Manager and Adobe Connect since Adobe Learning Manager redirects the Learner to Adobe Connect using the same email ID.

### FAQs

**Q. Does the learner have to attend the live session?**
**A.** No. A learner who misses the live session can still be marked as attended by watching the recording for long enough.

**Q. How much of the recording must the learner watch?**
**A.** The percentage in the completion criteria, applied to the recording duration. For example, at 50% a 5-minute recording needs at least 2.5 minutes of watch time.

**Q. Does skipping ahead in the recording count?**
**A.** No. Adobe Connect records the time the learner actually watched, so dragging the seek bar does not count.

**Q. Is attendance marked as soon as the learner finishes watching?**
**A.** No. Learning Manager pulls viewer data from Adobe Connect on a schedule, so attendance updates after the next pipeline run.

**Q. Does Adobe Connect send the data to Learning Manager?**
**A.** No. Learning Manager pulls it. It's a pull mechanism at the Adobe Connect instance level, not a push.

**Q. How does Learning Manager know which learner watched?**
**A.** Adobe Connect captures the learner's email and the recording watch time. Learning Manager maps that to the course and module.

**Q. Who controls how often the sync runs?**
**A.** The Integration Admin sets the schedule and can turn it on or off.

**Q. Is the completion percentage set for each instance?**
**A.** No. It is a common setting across the account.

**Q. Can multiday sessions share one Connect room?**
**A.** Yes. Authors can reuse the persistent room created for day 1 on the sessions for other days, and the room name appears at instance level in Learning Manager.
