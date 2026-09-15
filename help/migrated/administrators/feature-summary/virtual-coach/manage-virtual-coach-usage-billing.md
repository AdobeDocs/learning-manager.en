# Manage Virtual Coach usage and billing

Activate Virtual Coach, monitor Monthly Active User (MAU) credit consumption, and download learner performance reports as an Adobe Learning Manager administrator.

## Activate Virtual Coach for your account

Virtual Coach is available as an add-on to Adobe Learning Manager. After purchase, provisioning generates an activation key that's emailed to the account administrator.

1. Sign in to Adobe Learning Manager as an administrator.
2. Navigate to the **Billing** page from the left navigation pane.
3. In the **Virtual Coach** section, enter the activation key you received by email.

   ![](/help/migrated/administrators/feature-summary/assets/virtual_coach12.png)
   *Enter your activation key in the Virtual Coach section of the Billing page to turn on the feature.*

4. Select **Apply**. Virtual Coach is enabled for your account.

Once activated, you receive an in-app notification confirming the feature is live. Four sample role-play scenarios are added automatically to the **Content Library** so authors can begin immediately.

>[!NOTE]
>
>The activation key is auto-generated during provisioning and shared by email. If you don't have the activation key, contact your Adobe Learning Manager Customer Success Manager.

## View your MAU credit balance

Monthly Active User (MAU) credits count the number of unique learners who use Virtual Coach each month.

1. Navigate to the **Billing** page.
2. In the **Virtual Coach** section, select **View Usage Details**.

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach22.png)

3. Use the **Select period** drop-down to choose the date range you want to review.

   The **Overall Usage** table shows:

   - **Available**: total MAU credits purchased.
   - **Used**: credits consumed to date.
   - **Remaining**: credits available for the rest of the contract period.

   The **Monthly Usage** table shows the number of unique active learners by calendar month.

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach23.png)

4. Select **Download Detailed Report** to export the full usage data.

## How MAU credits are consumed

An MAU credit is consumed when a learner completes a Virtual Coach session in a calendar month. Additional sessions by the same learner in the same month don't consume additional credits. Unused credits at the end of the contract period lapse and don't carry over.

| Scenario | MAUs consumed |
|---|---|
| One learner completes 5 sessions in January | 1 |
| The same learner uses Virtual Coach in both January and February | 2 (1 per month) |
| 100 learners each complete 1 session in January | 100 |

*MAU credits are counted per unique learner per calendar month, regardless of how many sessions each learner completes.*

**Example: single learner, multiple sessions.** Sarah completes 5 Virtual Coach sessions in January. She's counted as a single unique user for the month, so 1 MAU is consumed regardless of how many times she practices.

**Example: same learner, multiple months.** Sarah uses Virtual Coach in both January (3 sessions) and February (2 sessions). Each calendar month counts separately, so 2 MAUs are consumed — 1 for January and 1 for February.

**Example: multiple learners, same month.** 100 sales reps each complete 1 Virtual Coach session in January. Each unique learner counts as one MAU for that month, so 100 MAUs are consumed.

**Example: team practice over time.** Your team of 50 people uses Virtual Coach throughout the year. In a month where only 5 of the 50 practice, 5 MAUs are consumed for that month; in a month where all 50 practice again, 0 additional MAUs beyond what's already been consumed for returning learners that month, since each learner is only counted once per calendar month regardless of how many times they practice within it.

## View Virtual Coach reports

The **Reports** > **AI Reports** page provides usage and performance data for all Virtual Coach activity across your organization. All reports are exported in CSV format; report generation may take several minutes depending on the data size.

![The AI Reports page, showing the Virtual Coach section with two report links: Learner Usage Summary and Session Details.](/help/migrated/administrators/feature-summary/assets/virtual_coach13.png)
*Download the Learner Usage Summary or Session Details report from the AI Reports page.*

Two reports are available under the **Virtual Coach** heading:

- **Learner Usage Summary**: contains monthly usage data for all learners. Use this report to track how many learners are using Virtual Coach each month, monitor MAU credit consumption, and identify engagement trends over time.
- **Session Details**: contains session-level data for all learners over the last 90 days. Use this report to review individual session scores, topic coverage, and style metrics across your learner population, and to identify skill gaps that may require additional training or content.

### Access and download a report

1. Sign in to Adobe Learning Manager as an administrator.
2. Select **Reports** in the left navigation pane.
3. Select **AI Reports**.
4. Under the **Virtual Coach** section, select the report you want to download: **Learner Usage Summary** or **Session Details**.
5. Select the date range when prompted, then select **Proceed**.
6. The report downloads automatically as a CSV file.

For answers to common licensing and usage questions, see the [Adobe Learning Manager Virtual Coach FAQ](/help/migrated/authors/feature-summary/virtual-coach/virtual-coach-faq.md).
