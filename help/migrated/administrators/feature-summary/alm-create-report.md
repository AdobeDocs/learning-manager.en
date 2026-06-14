---
jcr-language: en_us
title: Get started with a Report Builder template  
description: Create a report quickly in Adobe Learning Manager Report Builder by starting from a pre-built template for common use cases.   
contentowner: mmanuel
---

# Get started with a Report Builder template  

Templates are ready-to-use report configurations provided by Adobe Learning Manager. Each template is designed for a specific use case, such as enrollment and completion tracking, compliance reporting, or instructor performance. You can download a template directly or duplicate it to create an editable copy.

1. Log in to Adobe Learning Manager as an administrator.  
2. Select **Reports** in the left pane and then select **Report Builder**.  
3. Select the **Templates** tab.  
4. Browse the available templates. Each template is named for its use case.
    ![](assets/image-007.png)  
5. Select a template name to open its read-only preview. For this example, select Duplicate near the Catalog Wise - Course Count MoM template. Review the columns, applied filters, and sort order. When you duplicate a template, Report Builder opens an editable copy with the template's existing configuration pre-loaded. The report name, description, columns, filters, and sorting are all editable before you save.  

## Name and describe the report

1. In the **Name** field, replace the default name (for example, _copy of Catalog Wise_ - _Course Count MoM_) with a unique name for your report. A name is required.  
2. In the **Description** field, enter a short summary of what the report contains. This helps other admins understand the report's purpose when they view or edit it.  

## Add and configure columns

The **Columns** section has two panels: **Select columns** on the left and **Selected Columns** on the right.

### Add a column

1. In the **Select columns** panel, expand a dataset by selecting its name. For example, **Catalog** or **Active Field User Group**.  
2. Select the **+** icon next to the column you want to add. The column appears in the **Selected Columns** panel on the right.
 ![](assets/image-009.png)   
3. To add the same column more than once. For example, to apply two different aggregates to the same field. Select **+** again for that column.  

### Reorder columns

Drag the handle on the left of any column row in the **Selected Columns** panel to move it to a different position. The column order in the panel matches that in the downloaded report.

### Rename a column

1. Select the **edit** (pencil) icon on a column row.
    ![](assets/image-011.png)   
2. Enter an alias. The alias appears as the column header in the downloaded report instead of the default field name.
    ![](assets/image-013.png)   

### Remove a column

Select the **×** icon on a column row to remove it from the report.

## Apply group by

The **Group by** control appears at the top of the **Selected Columns** panel.

1. Select **Group by: Select**.
    ![](assets/image-015.png)   
2. Select the columns to group by. You can select more than one. In the screenshot, the report is grouped by _catalog_ and _Creation month_.  
3. Each selected group-by column appears as a tag below the Group by control. To remove a group-by column, select **×** on its tag.  

>[!NOTE]
>
>When group by is applied, every column that is not a group-by column must have an aggregate function applied. A column without an aggregate will cause an error.

## Apply an aggregate to a column

1. On any non-group-by column in the **Selected Columns** panel, select **Aggregate by**.  
2. Choose a function from the dropdown. In the screenshot, **Learning Object** - **Learning Object ID** uses **Count Distinct**, aliased as ount_of_course.  

Available aggregate functions:

| Function | What it returns |
|----------|-----------------|
| Count | Total number of rows in the group |
| Count Distinct | Number of unique values in the group |
| Count If | Number of rows matching a value you specify |
| Sum | Total of a numeric field across the group |
| Min | Lowest value in the group |
| Max | Highest value in the group |
| Average | Mean value across the group |

## Apply filters

The **Filters** section is below the **Columns** section. Filters restrict which rows appear in the report.

1. To add a filter, select the **+** icon at the right of the Filters section.  
2. Choose the field to filter on.
    ![](assets/image-017.png)
3. Select an operator and enter or choose a value.  

To edit an existing filter, select the **pencil** icon on the filter row. To add a nested filter group, select the + icon with brackets on the right of a filter row.

## Configure sorting

The Sorting section is below the Filters section.

1. Select **+ Add sorting** to add a sort.  
2. Choose the column to sort by and select **Ascending** or **Descending**.
    ![](assets/image-020.png)  
3. Repeat to add secondary sorts. Drag the handle on the left of each sort row to change priority.  

>[!TIP]
>
>Always apply at least one sort. Without sorting, row order may differ between downloads of the same report.

## Save the report

Select **Save Report** in the top-right corner. The report is saved to your **Reports** tab and is ready to download.

## Best practices

* Use aliases on every column so the downloaded report has meaningful headers instead of field names like _Learning Object_ - _Learning Object ID_.  
* Use Count Distinct instead of Count when you want unique records, for example, distinct courses per catalog rather than total rows.  
* Apply sorting before saving, especially for reports you'll share or subscribe to.  
* Keep the description up to date. Other admins rely on it to understand the report's scope without opening it.
