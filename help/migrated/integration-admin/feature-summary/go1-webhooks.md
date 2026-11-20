---
description: Learn how Go1 completion webhooks help Adobe Learning Manager capture course completions, even when learners close the browser early
jcr-language: en_us
title: Go1 completion tracking with webhooks
exl-id: 25c9c401-905f-4408-89ac-ac630a45a0c7
---

# Go1 completion tracking with webhooks

## Overview

Adobe Learning Manager now supports webhook-based completion tracking for Go1 content. This enhancement improves the reliability of course completion synchronization between Go1 and Learning Manager. Completion events are captured even when learners exit the course player right after finishing a course.

Go1 uses webhooks to send course completion notifications to Learning Manager whenever a learner completes a Go1 course. Learning Manager receives and processes these completion events independently of the learner's browser session.

Go1 also retries the webhook delivery until Learning Manager acknowledges receipt of the completion event. This helps prevent missed or incomplete learning records.

## Problem this enhancement solves

Previously, completion tracking relied on communication between the Go1 player and Learning Manager while the learner's browser session remained active. If a learner closed the browser window or navigated away before the completion status was fully processed, the completion record could be lost.

As a result:

* Course completions might not appear in learner transcripts.
* Administrators could find discrepancies between actual and recorded completions.
* Missed completion events couldn't be recovered automatically.

## Event workflow

1. A learner launches and completes a Go1 course.
1. Go1 records the completion.
1. Go1 sends a completion webhook to Learning Manager.
1. Learning Manager validates and accepts the completion event.
1. Learning Manager updates the learner's completion status.
1. If Learning Manager doesn't acknowledge the event, Go1 automatically retries delivery.

## Frequently asked questions

**Does this change require administrator configuration**

No, this change doesn't require any administrator configuration.

**Are existing Go1 courses affected**

No, existing Go1 courses aren't affected. The enhancement improves completion synchronization for Go1 content.

**What happens if a learner closes the browser early**

Go1 sends the completion webhook independently of the learner's browser session. Even if the learner exits the course player, Go1 keeps retrying delivery until Learning Manager acknowledges the completion event.
