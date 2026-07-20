---
description: Insights Agent is an AI-powered feature in Adobe Learning Manager that lets administrators query learner data using natural language.
jcr-language: en_us
title: Insights Agent (beta) in Adobe Learning Manager
---

# What is Insights Agent

Insights Agent is an AI-powered feature in Adobe Learning Manager that lets administrators query learner data using natural language. Instead of downloading reports and manipulating spreadsheets, you type a question, such as "How many courses were created in the last 3 months in the account? Give me a month-on-month report.", and Insights Agent retrieves and presents the data directly. You can view results as tables or download them as a CSV file.

Insights Agent is designed to reduce the steps between having a data question and getting an answer. Administrators who currently rely on Excel pivots, BI teams, or multiple combined reports can use Insights Agent to get answers faster.

## What Insights Agent can do

You can use Insights Agent to:

- Check completion and compliance metrics by region, department, or user group
- Analyze enrollment trends across learning programs
- View progress data for a specific course or learning path
- Retrieve results in a table or as a downloadable CSV file
- Get a plain-language explanation of how your results were calculated

## What data Insights Agent does not support

The following data types are outside the scope of this release:

- Feedback and survey data
- Gamification points and badges
- Audit history and change logs

Queries that reference these data types will not return results. For example, "How many gamification points were awarded last quarter?" or "Which learners have earned a compliance badge?" will return an error or incomplete data.

## How Insights Agent differs from Report Builder

Both features use the same underlying learning data, but they work differently. Insights Agent is conversational. You describe what you want, and the agent retrieves it. Report Builder is structured. You select datasets, columns, and filters to build reusable reports.

| **Use case** | **Recommendation** |
|---|---|
| Ask a quick data question | Insights Agent |
| Explore data without knowing the schema | Insights Agent |
| Build a structured, repeatable report | Report Builder |
| Combine multiple datasets with custom joins | Report Builder |
| Schedule report subscriptions | Report Builder |
| Combine datasets with custom joins or advanced data modeling | Report Builder |

**IMPORTANT**: Integration between Insights Agent and Report Builder is planned for a future release and is not available in the current beta.

## How Insights Agent works

When you enter a question, Insights Agent processes it in four stages:

1.**Interpretation**: The agent parses your question to identify what data is needed. If any part of the question is ambiguous, the agent asks you a clarifying question before proceeding

2.**Approach**: The agent describes the steps it took to find your answer. This section helps you verify that the data was retrieved the way you intended, especially for complex queries.

3.**Results**: The agent presents your data as a table. If your results contain 50 or fewer rows, a plain-language summary may be included.

4.**Download**: You can download the results as a CSV file. Large reports may take additional time; the agent notifies you when the file is ready.

The **Approach** section is particularly useful for complex queries. It shows the logic the agent used, similar to what a BI analyst would explain if they ran the query manually. Reviewing the approach helps you confirm that the output is reliable before you act on it.

## Ask questions using Insights Agent

Use Insights Agent in Adobe Learning Manager to query learner data with plain-language questions and get results as text, tables, or downloadable CSV files.

Insights Agent is available to admins from the AI assistant panel in Learning Manager. The panel is resizable. You can expand it to make results easier to read. By default, the **Get Insights** mode is selected when you open the panel. A separate **Learn** mode is also available for instructional questions about how to use the product. **Learn** mode answers instructional questions about how to use Learning Manager. For example, "How do I create a learning path?" It does not query learner data.

### Ask a question

When the **Get Insights** mode is selected by default, you can immediately start querying learner data without needing to adjust the mode each time you access the assistant. However, if you ever switch to the **Learn** mode for instructional questions, make sure to re-select **Get Insights** before submitting a query.

1.Select the AI assistant icon in Learning Manager to open the assistant panel.

2.Select **Get Insights** in the mode selector, if not already selected by default.

![](assets/ask-question.png)

3.Type your question in the text field. Use plain language. For example: **How many courses were created in the last 3 months?**

4.Select **Send** or press **Enter** to submit your question.

