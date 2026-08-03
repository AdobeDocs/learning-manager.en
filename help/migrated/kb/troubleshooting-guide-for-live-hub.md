---
title: Troubleshooting Guide for Live Hub
description: Common error messages and notifications you may encounter during a Live Hub session, their causes, and steps to resolve them.
---

# Troubleshooting Guide for Live Hub

During a Live Hub session, Instructors may encounter error messages or notifications that prevent certain actions from completing as expected. This article describes common instructor-facing errors, their possible causes, and the steps you can take to resolve them.

## Quiz tab issues

The messages below can appear when an Instructor creates or launches a quiz, and the quiz doesn't meet the requirements needed to launch it.

|Error message|Scenario|Suggestions to overcome the error|
|---|---|---|
|Enter a question to continue.|An Instructor tries to launch a quiz without entering the question text.|Enter the question, provide the answer options, select the correct answer, and then launch the quiz for participants.|
|Answer options can't be left blank.|An Instructor enters the question text but doesn't enter the answer options or leaves one or more answer options blank.|Enter the question, provide the answer options, select the correct answer, and then launch the quiz for participants.|
|Mark the correct answer.|An Instructor enters the question and answer options but doesn't select a correct answer option.|Enter the question, provide the answer options, select the correct answer, and then launch the quiz for participants.|

## Poll tab issues

The messages below can appear when an Instructor duplicates, deletes, or resets a poll.

|Error message|Scenario|Suggestions to overcome the error|
|---|---|---|
|Couldn't duplicate the poll. Please try again.|An Instructor duplicates an existing poll, and the duplicate doesn't get created.|Close the Polls & Quizzes panel and retry duplicating the poll.|
|Couldn't delete all polls. Please try again.|An Instructor deletes all polls at once using Delete all, and the bulk delete fails or only partially completes.|Close the Polls & Quizzes panel and retry deleting the polls using Delete all polls.|
|Couldn't delete the poll. Please try again.|An Instructor deletes a single poll, and the deletion doesn't complete.|Close the Polls & Quizzes panel and retry deleting the poll.|
|Couldn't reset the poll. Please try again.|An Instructor resets a previously run poll so it can be reused, and the reset doesn't complete.|Close the Polls & Quizzes panel and retry resetting the poll.|

## Upload content

The message below can appear when an Instructor uploads a reference file that the AI assistant uses to answer questions.

|Error message|Scenario|Suggestions to overcome the error|
|---|---|---|
|Couldn't process the file. Please try again.|An Instructor uploads a corrupt, blank, or password protected file that can't be processed.|Convert the file to a supported format (PDF or PPT) and upload it again.|

## Upload content toast issues

The messages below appear as toast notifications when an Instructor uploads a reference file that the AI assistant will use, and the file fails a specific validation check.

|Error message|Scenario|Suggestions to overcome the error|
|---|---|---|
|File could not be processed. Please check the file and try again.|An Instructor uploads a file that is corrupt.|Check the file format and convert it to a supported format (PDF or PPT), then re-upload.|
|File is password protected. Please remove the password and re-upload.|An Instructor uploads a file that is password protected.|Remove the password protection from the file, then re-upload it.|
|File has no content to process. Please upload a file with text content.|An Instructor uploads a file that has no content for the AI assistant to process.|Upload a file that contains text content.|
|"FileName.pdf" exceeds the 1 MB limit.|An Instructor uploads a PDF file that exceeds the 1 MB file size limit.|Compress or reduce the PDF file size to under 1 MB, then re-upload.|
|"FileName.pptx" exceeds the 3 MB limit.|An Instructor uploads a PPT file that exceeds the 3 MB file size limit.|Compress or reduce the PPT file size to under 3 MB, then re-upload.|

## Breakout rooms issues

The messages below can appear when an Instructor tries to start breakout rooms.

|Error message|Scenario|Suggestions to overcome the error|
|---|---|---|
|Cannot start breakout — connection is interrupted. Please try again when reconnected.|An Instructor tries to start breakout rooms while their connection is currently interrupted or reconnecting.|Wait for your connection to stabilize (watch for a reconnect indicator), and then start breakout rooms again.|
|Breakout could not be started. Please try again.|An Instructor starts breakout rooms, and the request to start them fails.|Retry starting breakout rooms. If it persists, close the Breakouts panel and try again.|

## Answer generation toast issues

The message below can appear when an Instructor asks the AI assistant to generate an answer to a Participant's question in chat.

|Error message|Scenario|Suggestions to overcome the error|
|---|---|---|
|This wasn't covered in the session.|A learner asks a question that isn't covered in the uploaded content reference. This is expected behavior, not an error.|Answer the question manually.|
