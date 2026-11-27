---
title: Track the participant engagement
description: Learn how Instructors use the real-time participant engagement indicator in Live Hub to monitor browser focus, chat activity, and poll participation.
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
---

# Track the participant engagement

Participant engagement in Live Hub gives Instructors a real-time view of Learner or participant engagement during a live session. It combines browser focus, chat activity, and poll participation into a single engagement level, shown as a green, yellow, or red indicator. Use it to spot dips in attention and adjust your delivery in real time.

The participant engagement displays the average engagement level of all learners in the main room at a given point in time. The level refreshes as soon as a Learner joins the session.

The participant engagement is calculated and displayed only during a live session.

>[!NOTE]
>
> Only Instructors can see the participant engagement. Learners don't have access to it.

## Understand engagement level calculations

The participant engagement score helps you monitor learner attentiveness in real time during a live session. This engagement badge at the top of the screen displays the overall engagement level as **Low**, **Medium**, or **High**, allowing you to adjust your session delivery and encourage participation as needed.

The indicator is visible only to Instructors in the main room.

![Engagement Level Indicator](assets/engagement-level-indicator.png)
*Live Hub interface displaying the participant engagement in the upper right corner.*

## How is engagement score calculated

Each learner or participant has engagement score ranging from 0 to 100, based on the following factors:

- **Attention to the session**: When a learner or participant keeps the session window active, their engagement level is High by default. If they switch to another window or browser tab, their engagement level drops to Low unless they continue participating in session activities.
- **Participation in the session**: Activities such as speaking, sharing a screen, sending chat messages, responding to polls or quizzes, drawing on the whiteboard, raising a hand, sending reactions, and clicking within the session increase the engagement score.

### How engagement scores change

Learner engagement score changes throughout a live session based on their attention and participation. The following conditions affect how the engagement score is calculated:

- **Activity duration**: Most participation activities temporarily increase the engagement score, with their contribution gradually decreasing over approximately five minutes. For example, if a learner speaks during a session and then switches to another window, their engagement score decreases gradually rather than immediately
- **Screen sharing**: The engagement score remains at 100 while a Learner or a participant shares their screen.
- **Simultaneous activities**: When a Learner or a participant performs multiple activities simultaneously, only the activity with the highest engagement value is considered. The scores from individual activities are not combined, ensuring that the engagement score does not exceed 100.
- **Multiple devices**: If a Learner or a participant joins the session from multiple devices, the highest engagement score across those devices is considered.

## Overall engagement score

The participant engagement badge displays the overall engagement level based on the average engagement score of all learners in the main room, rounded to the nearest whole number.

The following conditions apply when calculating the overall engagement score:
- **Instructors and recording bots**: Instructors and recording bots are excluded from the overall engagement score calculation. Recording bots do not appear in the attendee list.
- **Breakout rooms**: Learners or participants in breakout rooms are not included in the overall engagement score. When learners move between the main room and a breakout room, their individual engagement scores reset and are recalculated within one to two minutes.
- **New learners**: Participant engagement score becomes available approximately one minute after joining the session. Until the score is available, the learner or participant is excluded from the overall engagement score calculation.
- **Empty main room**: When no learners or participants are present in the main room, the badge displays Participant engagement without an engagement level.

## Identify engagement levels and indicators

The participant engagement badge displays one of the following engagement levels based on the overall engagement score. You can use these levels to monitor learner attentiveness and adjust your session delivery as needed.  Here's what each level means:

| **Engagement level** | **Score** | **Description** |
|----|----|----|
| High | 61 to 100 | Learners actively participate in the session. |
| Medium | 31 to 60 | Learners show occasional interaction with moderate participation. |
| Low | 0 to 30 | Learners show minimal or no interaction or reduced focus during the session. |

>[!NOTE]
>
> - The engagement score indicates participant attention during a session. It does not measure learning outcomes or performance.
> 
> - Engagement scores are calculated every minute. Changes may take up to two minutes to appear in the engagement badge.

## Frequently Asked Questions

+++ Does the engagement score detect whether a participant is actively watching the session?

No. The engagement score is calculated based on whether the session window is active and the participant's activities, such as speaking, sending chat messages, and responding to polls. It does not use camera video, eye tracking, or microphone mute status to measure engagement.

+++

+++ What happens when a participant switches away from the session window?

When a participant switches to another browser tab, window, or application, the session window is no longer considered active. Even if the session window remains visible, it is considered inactive when another window is in focus.

+++

+++ Do all participation activities contribute equally to the engagement score?

Speaking, screen sharing, sending chat messages, responding to polls or quizzes, drawing on the whiteboard, raising a hand, and sending reactions contribute equally to the engagement score. Clicking within the session contributes slightly less.

+++

+++ How does the engagement score change after a participation activity?

The contribution of most participation activities gradually decreases over approximately five minutes. For example, if a participant switches to another window and then speaks, their engagement score increases to 100 at the next update. Over the following minutes, the score gradually decreases to 80, 60, 40, and 20, where it remains until the participant returns to the session window or participates again.

A participant who keeps the session window active maintains a High engagement level.

+++

+++ Are participants in breakout rooms included in the overall engagement score?

No. Only participants in the main room are included in the overall engagement score calculation. The engagement badge is not displayed when an instructor is in a breakout room.

+++

+++ Why does the overall engagement score decrease after breakout rooms end?

When participants move from breakout rooms to the main room, their individual engagement scores reset and are recalculated within one to two minutes. This can temporarily decrease the overall engagement score.

+++

+++ How is the engagement score calculated when a participant joins from multiple devices?

If a participant joins the session from multiple devices, the highest engagement score across those devices is considered. An inactive session on one device does not reduce the engagement score recorded on another active device.

+++

+++ Why does the engagement badge take up to two minutes to update?

Each participant's engagement score is calculated once every minute. The overall engagement score is then updated once every minute, so changes can take up to two minutes to appear in the engagement badge.

+++

+++ What can instructors do when the engagement badge displays Low?

A Low engagement level indicates that most participants have switched away from the session window and are not actively participating. Instructors can use polls, quizzes, chat prompts, or discussion questions to encourage participation and bring participants' attention back to the session.

+++

+++ Can Instructors use engagement scores to track attendance or evaluate learners?

Engagement scores provide a general indication of participant attention and activity during a session. A participant can maintain a High engagement level by keeping the session window active, even without actively participating or demonstrating learning. Therefore, engagement scores may not be suitable for evaluating learner performance or tracking attendance.

+++

+++ Can participants view their engagement scores?

No. The engagement badge is visible only to Instructors.

+++

+++ Can Instructors view individual participants' engagement scores?

No. The engagement badge displays only the overall engagement score for the main room. Individual participant scores are not available.

+++

+++ Can Instructors disable engagement tracking?

No. Engagement tracking is always enabled and cannot be disabled.

+++

+++ Are engagement scores available in reports or session history?

No. The engagement badge displays only the current overall engagement score. Engagement scores are not saved or included in reports or session history.

+++

+++ Can co-instructors view the engagement badge?

Yes. Co-instructors can also view the engagement badge during a session.

+++

+++ How are engagement scores calculated on mobile devices?

Participants can access Live Hub sessions through mobile browsers. Engagement scores are calculated using the same criteria as desktop browsers.

+++