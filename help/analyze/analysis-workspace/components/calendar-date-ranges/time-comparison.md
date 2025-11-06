---
description: 了解如何在 Analysis Workspace 中使用日期对比功能，该功能可让您基于包含日期范围的任意列创建通用的日期对比分析。
title: 日期比较
feature: Date Ranges
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: 27ec105290ea4d093251fc6cf537d57a94015403
workflow-type: ht
source-wordcount: '755'
ht-degree: 100%

---

# 日期比较

Analysis Workspace 中的日期对比功能可让您基于包含日期范围的任意列创建常见的日期对比分析，例如：同比（年对年）、环比（季对季、月对月）等。

## 比较时段

分析需要上下文，而这种上下文往往来自前一个时段。例如，问题&#x200B;*“相比去年同期，目前的表现提升了多少，或有所下降？”* 是理解您的业务的基础。日期对比功能会自动包含一个&#x200B;*差异*&#x200B;列，用于显示与指定时段相比的百分比变化。

1. 创建一个[自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)，自由选择您希望在指定时段内进行对比的维度和量度。
1. 在面板或列中设置时间范围，以确定比较的时间周期，并指定是滚动时间比较还是固定时间比较。

   要创建滚动时间比较，请将面板或列的日期范围设置为滚动日期范围（例如&#x200B;**[!UICONTROL 最近 7 天]**、**[!UICONTROL 最近 30 天]**&#x200B;等）。

   要创建固定时间比较，请将面板或列的日期范围设置为自定义日期范围。
1. 打开表格行的上下文菜单，然后选择&#x200B;**[!UICONTROL 比较时段]**。

   ![已选择“比较时段”的表格行](assets/compare-time.png)

   >[!NOTE]
   >
   >此上下文菜单选项在量度行、日期范围行和时间维度行中被禁用。

1. 根据您为表格设置的日期范围，您可以选择以下比较方式：

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 相对于该日期范围的前 *x* 周／月／季／年]** | 与紧邻该日期范围之前的所选日期范围进行比较。 |
   | **[!UICONTROL 去年与该日期范围对应的 x 周／月／季／年]** | 与一年前的相同日期范围进行比较。 |
   | **[!UICONTROL 将日期范围自定义为该日期范围]** | 允许您自定义日期范围。 |

   >[!NOTE]
   >
   >如果您选择自定义天数，例如 10 月 7 日至 10 月 20 日（14 天范围），您将只获得 2 个选项：**[!UICONTROL 在此日期范围之前的 14 天]**&#x200B;和&#x200B;**[!UICONTROL 将日期范围自定义为此日期范围]**。

1. 生成的对比结果如下所示：

   ![自由格式表格，显示日期范围对比及百分比变化。](assets/compare-time-result.png)

   “百分比变化”列中的数值为负时显示为红色，为正时显示为绿色。

## 添加用于对比的时段列

您现在可以为表格中的每一列添加一个时间段，此操作允许您添加一个不用于日程表设置的时段。

1. 右键单击表格中的列并选择&#x200B;**[!UICONTROL 添加时间段列]**。

   ![](assets/add-time-period-column.png)

1. 根据您为表格设置的日期范围，您可以选择以下比较方式：

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 相对于该日期范围的前 *x* 周／月／季／年]** | 添加包含周／月等时间单位的列。紧邻该日期范围之前的时段。 |
   | **[!UICONTROL 去年与该日期范围对应的 *x* 周／月／季／年]** | 添加一年前的同一日期范围。 |
   | **[!UICONTROL 将日期范围自定义为此日期范围]** | 允许您创建自定义日期范围。 |

   >[!NOTE]
   >
   >如果您选择自定义天数，例如 10 月 7 日至 10 月 20 日（14 天范围），您将只获得 2 个选项：**[!UICONTROL 在此日期范围之前的 14 天]**&#x200B;和&#x200B;**[!UICONTROL 将日期范围自定义为此日期范围]**。

1. 时段会被插入到选定列的顶部：

   ![自由格式表格，显示当前日历周期与上一个日历月份的事件发生次数。](assets/add-time-period-column2.png)

1. 您可以根据需要添加任意数量的时间列，还可以混合和匹配不同的日期范围：

1. 此外，您还可以对各列进行排序，排序依据的不同会改变日期的排列顺序。

## 将列日期调整为从同一行开始

您可以将每列的日期调整为全部从同一行开始。

例如，您可以对上一周（截至 2024 年 10 月 5 日）与前一周进行按日对比分析。默认情况下，左侧列将从 9 月 22 日开始，右侧列将从 9 月 29 日开始。

![日期未对齐](assets/not-align-dates.png)

您可以在自由格式表格可视化的[设置](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1)中启用&#x200B;**[!UICONTROL 对齐日期，使各列的日期从同一行开始]**，从而实现日期对齐。

![](assets/align-dates.png)

使用此选项时，请考虑以下事项：

* 所有新项目均默认启用此设置。

* 此设置适用于整个表格。例如，如果您在表格中的某个细分中更改此设置，该设置将应用于整个表格。


<!--
# Date comparison

Date comparison in Analysis Workspace lets you take any column containing a date range and create a common date comparison, such as: year-over-year, quarter-over-quarter, month-over-month, etc.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Date comparison](https://video.tv.adobe.com/v/30753?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



## Compare time periods {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL Compare Time Periods] leverages advanced Calculated Metrics. As a result, it is available only to customers with Analytics Select, Prime, and Ultimate SKUs. 

Analysis requires context, and often that context is provided by a previous time period. For example, the question "How much better or worse are we doing than at this time last year?" is fundamental to understanding your business. Date Comparison automatically include a "difference" column, which shows the percentage change compared to a specified time period.

1. Create a Freeform table, with any dimensions and metrics you want to compare over a time period.
1. Right-click a table row and select **[!UICONTROL Compare time periods]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >This right-click option is disabled for metric rows, date range rows, and time dimension rows.

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Compares to the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Compares to the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The resulting comparison looks like this:

   ![](assets/compare-time-result.png)

   Rows in the Percent Change column appear red for negative values and green for positive values.

1. (Optional) As in any other Workspace projects, you can create visualizations based on these time comparisons. For example, here is a Bar graph:

   ![](assets/compare-time-barchart.png)

   Note that in order to show the percentage change in the bar chart, you have to have the [!UICONTROL Percentages] setting checked in the [!UICONTROL Visualization Settings].

## Add a time period column for comparison {#section_93CC2B4F48504125BEC104046A32EB93}

You can now add a time period to each column in a table, enabling you to add a time period that is different from the one your calendar is set to. This is another way you can compare dates.

1. Right-click a column in the table and select **[!UICONTROL Add time period column]**. 

   ![](assets/add-time-period-column.png)

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Adds a column with the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Adds the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The time period will be inserted on top of the column you selected:

   ![](assets/add-time-period-column2.png)

1. You can add as many time columns as you want, as well as mix and match different date ranges:

   ![](assets/add-time-period-column4.png)

1. In addition, you can sort on each column, which will change the order of days depending on the column you are sorting on.

## Align column dates to start on the same row {#section_5085E200082048CB899C3F355062A733}

You can align the dates from each column to all start on the same row. 

For example, when you choose to align the dates, if you do a month-over-month comparison between October and September 2016, the left column will start with October 1 and the right column will start with September 1:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Consider the following when using this option:
>
>* This setting is enabled by default for all new projects.
>
>* This setting applies to the entire table. For example, if you change this setting for a breakdown within the table, it will change the setting for the entire table.
>

To enable this setting, if it is not already enabled:

1. In the table where you want to align column dates, select the **Settings** icon in the table header.

1. On the [!UICONTROL **Settings**] tab, select **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**.

![](assets/date-comparison-setting.png)


-->