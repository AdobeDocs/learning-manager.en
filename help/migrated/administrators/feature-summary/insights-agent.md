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

1. **Interpretation**: The agent parses your question to identify what data is needed. If any part of the question is ambiguous, the agent asks you a clarifying question before proceeding

2. **Approach**: The agent describes the steps it took to find your answer. This section helps you verify that the data was retrieved the way you intended, especially for complex queries.

3. **Results**: The agent presents your data as a table. If your results contain 50 or fewer rows, a plain-language summary may be included.

4. **Download**: You can download the results as a CSV file. Large reports may take additional time; the agent notifies you when the file is ready.

The **Approach** section is particularly useful for complex queries. It shows the logic the agent used, similar to what a BI analyst would explain if they ran the query manually. Reviewing the approach helps you confirm that the output is reliable before you act on it.

## Ask questions using Insights Agent

Use Insights Agent in Adobe Learning Manager to query learner data with plain-language questions and get results as text, tables, or downloadable CSV files.

Insights Agent is available to admins from the AI assistant panel in Learning Manager. The panel is resizable. You can expand it to make results easier to read. By default, the **Get Insights** mode is selected when you open the panel. A separate **Learn** mode is also available for instructional questions about how to use the product. **Learn** mode answers instructional questions about how to use Learning Manager. For example, "How do I create a learning path?" It does not query learner data.

### Ask a question

When the **Get Insights** mode is selected by default, you can immediately start querying learner data without needing to adjust the mode each time you access the assistant. However, if you ever switch to the **Learn** mode for instructional questions, make sure to re-select **Get Insights** before submitting a query.

1. Select the AI assistant icon in Learning Manager to open the assistant panel.

2. Select **Get Insights** in the mode selector, if not already selected by default.
![](assets/ask-question.png)

3. Type your question in the text field. Use plain language. For example: **How many courses were created in the last 3 months?**

4. Select **Send** or press **Enter** to submit your question.

### Review the response

After you submit your question, Insights Agent processes your request and returns a response with up to four parts:

1. **Disambiguation (if needed):** If your question contains an ambiguous term, such as \"learning activity\" or \"performance\", or "Give me performance data from last 3 months", the assistant displays a list of options and asks you to select one before it proceeds. Select the option that best matches what you\'re looking for. After the initial question, you cannot type additional instructions. Selecting from the provided options is the only interaction available until you start a new query using the query interface. You can only respond to disambiguation by selecting from the provided options; free-text follow-up is not available in this release.

![](assets/disambiguation.png)
2. **Approach:** The **Approach** section describes the steps the agent took to retrieve your data. It appears as a scrollable panel below the question. Select the expand icon to view the full approach. Reviewing this section helps you confirm that the logic matches your intent, especially for complex queries. For example, if you ask for \"all learners enrolled in the last year,\" the agent may return each learner\'s most recent enrollment rather than every enrollment record. The **Approach** section **may** or **will explain** that decision. If the logic doesn\'t match your intent, start a new query with more specific terms.

![](assets/approach.png)
3. **Results:** The Insights Agent generates results as text or a table. For data points that are best interpreted in a tabular format, the Insights Agent returns a table. The Insights Agent does not generate charts or graphs. To visualize the data, download the CSV and open it in your preferred tool. If your results contain 50 or fewer rows, a plain-language summary may be included above the table. For example, \"Which courses do not have less than 5 enrolments that were created in the last 1 year, and who are the authors?\"

![](assets/results.png)

And the response contains the following summary:

***Summary***

- *Matched courses: 102*
- *Enrolment count range: 24 to 2019*
- *Average enrolments per matched course: 589.6*
- *Median enrolments per matched course: 553.5*

*A download link for the full report will be provided once the export is ready.*

**Note:** Insights Agent is probabilistic. If you run the same query twice, the response phrasing or result ordering may differ slightly. The underlying data retrieved is the same, but the output can vary across runs.

### Download the report

Select **Download report** to export your results as a CSV file. For large result sets, the download may take additional time. The agent displays a message when the file is ready; you also receive a notification.

## Start a new query

Each Insights Agent session handles one question at a time. After you review your results, select **New question** to ask a different question. You cannot type a follow-up question in the same session or ask the agent to refine or expand on the results it returned.

![](assets/new-question.png)

>[!TIP]
>
>If you want to explore related data, start a new query that incorporates what you learned from the first. For example, after seeing enrollment totals by region, start a new query to check completion rates for the same region.

## Provide feedback

After each response, select the thumbs-up or thumbs-down icon to rate the result. You can also specify whether the output was inaccurate, difficult to understand, or took too long to return. This feedback helps improve the agent over time.

![](assets/feedback.png)

## Best practices

- Start with a specific question rather than a broad one. \"What is the completion rate for the Safety Training course in the North America user group?\" returns more useful results than \"Show me completion data.\"
- Use exact Adobe Learning Manager terms when naming content and learner groups. The query writing guide lists the correct terms to use.
- If the agent asks a clarifying question, treat it as a signal to refine your original query. The more specific your question, the fewer clarifications are needed.
- Review the **Approach** section before acting on the results, especially for compliance-related queries where accuracy is critical.


## Write effective queries for the Insights Agent

The quality of your query directly affects the quality of the results Insights Agent returns. A well-formed query includes three ingredients: context (what content and which learners), scope (status, time range, and user state), and columns (the exact fields you want in the output). Learn how to use the correct terminology, query structure, and example queries as starting points.

### The three-part query formula

Every effective Insights Agent query contains these three components:

| **Component** | **What it means** | **Example** |
|---|---|---|
| **Context** | The content and learners you're asking about | "...the New Hire Onboarding learning path, for Sales Associate learners in Location 101..." |
| **Scope** | Enrollment status, time range, and user state | "...who are enrolled but not yet completed, in the last 90 days..." |
| **Columns** | Every field you want in the output | "...show name, email, location, and enrollment date" |

Missing any one of these components leads to ambiguous results or a clarifying question from the agent.

### Use the correct ALM terms

Insights Agent matches your query against Adobe Learning Manager's data model. Using the wrong term can return incorrect or no results. Use the terms in the left column below.

| **Use this term** | **Not this** |
|---|---|
| **Learning Path** | Program / track / curriculum |
| **Course** | Module / class / lesson |
| **Certification** | Badge / certificate |
| **Learner** | Student / employee |
| **Session** | Class / scheduled date |
| **User group** | Team / department / cohort |
| **Active field** | Custom field / attribute |
| **Enrollment** | Registration / assignment |
| **Completion** | Finished / done / passed |
| **Catalog label** | Category / tag group |

Insights Agent is case-insensitive, but exact term matching improves accuracy.

### Anchor your content

Every query needs a content anchor so the agent knows which learning items to look at. You can anchor by any of the following:

| **Anchor type** | **Example** |
|---|---|
| Name | "...the New Hire Onboarding learning path" |
| Catalog | "...all learning paths in the Onboarding catalog" |
| Catalog label | "...all courses where catalog label Region = North" |
| Tag | "...all courses tagged Compliance" |
| Skill | "...all courses mapped to the Customer Service skill" |
| Compliance label | "...all compliance-labeled certifications" |
| Content type | "...all published courses" / "...all certifications" |

### Anchor your learners

Specify which learners to include using one of these methods:

- **Active field value** — "learners where active field Job Title = Sales Associate" or "learners where active field Location = 101"
- **User group** — "learners in the Sales Associates user group"
- **Session** — "learners enrolled in the 15 June session of the Workplace Safety course"

### Define your scope

Without a clear scope, results may include the wrong status, time period, or user state.

| **Scope type** | **Options** |
|---|---|
| Enrollment status | enrolled / completed / not enrolled / overdue |
| Time range | all time / last 30 days / last 90 days / specific date range |
| User state | active users only (default) / add "include deleted users" for inactive |

### Name every output column

If you don't specify columns, Insights Agent chooses them for you. Name every field you want in the output.

| **Vague** | **Specific** |
|---|---|
| "Show location numbers" | "For each location: total learners, enrolled count, not-enrolled count" |
| "Show completion rates" | "For each learning path: name, total enrolled, total completed, completion %" |
| "Show me who failed" | "Show learner name, email, course name, and completion status for learners who have not completed" |

### Example queries

Use these as starting points. Adapt them by replacing the content names, user groups, and time ranges that apply to your account.

**Completion and compliance**

- "What is the completion rate for the Safety Training course in the North America user group?"
- "Show completion rate by user group for all compliance-labeled courses. Include user group name, total enrolled, total completed, and completion %."
- "What is the compliance rate for all learners where active field Job Title = VP?"

**Enrollment analysis**

- "How many learners are enrolled in the New Hire Onboarding learning path, by location?"
- "Show enrollments by region for the last 90 days. Include region name and enrollment count."
- "List all learners enrolled in the Workplace Safety course but not yet completed — include name, email, and enrollment date."

**Program and course progress**

- "What is the completion status breakdown for the Leadership Development learning path- show completed, in progress, and not started counts."
- "How many learners completed the Data Privacy course last month?"

**Organizational views**

- "Show completion rate for all compliance-labeled certifications, grouped by department. Include department name, total enrolled, and completion %."
- "What is the enrollment distribution by region for the last 30 days?"

### Common mistakes to avoid

| **Avoid** | **Do this instead** |
|---|---|
| No content anchor ("show me everything") | Name the specific path, course, catalog, tag, or skill |
| Vague metric ("why are completions low?") | Ask a measurable question: "Which learning paths have completion rate below 30%, by location?" |
| Not specifying user state | Add "active users only" or "include deleted users" explicitly |
| Asking for predictions | Ask what the current data shows, not what will happen |
| Asking about unsupported data (feedback, skills, badges) | Use existing reports in the Reports section |
| Asking multiple questions in one query ("Show enrollments by region and also list who hasn't completed Safety Training") | Ask one focused question per query. The agent may answer only part of a compound query, with no guarantee the rest is addressed. |

## Limitations in the release

**Recurring certifications may show multiple options during the disambiguation step**

When you query data for a recurring certification, Insights Agent may display multiple options during the clarification step, one for each recurrence of the certification, instead of showing it as a single entry. Selecting any of these options may return incorrect or incomplete data. We recommend not using Insights Agent to query recurring certifications.

**Courses that are part of a recurring certification may show multiple options during the disambiguation step**

When you query data for a course that is associated with a recurring certification, Insights Agent may display multiple options during the clarification step, one for each version of the course created across certification cycles, instead of showing it as a single entry. Selecting any of these options may return incorrect or incomplete data.

**Newly added data may take up to 30 minutes to appear in results**

After content is created, learners are enrolled, or completion records are updated, it may take up to 30 minutes for that data to be available in query results. If your results appear incomplete or do not reflect recent activity, wait 30 minutes and try your query again.

**Enrollment and completion data includes both direct and indirect enrollments**

When you query enrollment or completion data for a course or learning path, Insights Agent returns a combined count that includes both direct enrollments (learners enrolled specifically in that course or learning path) and indirect enrollments (learners who accessed the same content as part of another learning path or certification). The results do not separate these two enrollment types.

**Queries submitted in non-Latin scripts are not supported**

Insights Agent supports queries written in English and Latin-alphabet languages such as French and Spanish. Queries submitted using non-Latin scripts, including Japanese, Chinese, Arabic, Korean, Hindi, and Russian, cannot be processed, and the agent will display a message indicating the query could not be completed. If you submit a query in one of these languages, start a new query and rephrase it in English. Support for additional languages may be considered in future releases.

**Results may include content and learners in all states**

When you query data in Insights Agent, results may include records across all available states unless you specify otherwise. For example, a query for enrolled learners may include learners on a waitlist or learners whose accounts have been deleted. A query for courses or learning paths may include both published and retired content. To refine your results, include explicit conditions when you ask your question. For example, specify active users only, exclude waitlisted learners, or limit results to published content to ensure the output reflects only the records you intend to see.

