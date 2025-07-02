---
description: 了解如何在Analysis Workspace中使用日期比较，从中可选取包含日期范围的任何列，并创建常用的日期比较。
title: 日期比较
feature: Date Ranges
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: 3d15bd941cb8eaf20b8ae9f1ffa1dbfd403b2bfa
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 35%

---

# 日期比较

Analysis Workspace中的日期比较允许您采用包含日期范围的任何列来创建常见的日期比较，例如：年同比、季度同比、月同比，等等。

## 比较时间段

分析需要上下文，通常这类上下文是由前一时间段提供的。例如，问题&#x200B;*与去年的这个时候相比，您现在的表现要好多少或坏多少？*&#x200B;是了解您的业务的基础。 日期比较自动包括&#x200B;*差异*&#x200B;列，该列显示与指定时间段相比的百分比变化。

1. 创建一个[自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)，其中包含您要在一个时间段内比较的任何维度和量度。
1. 打开表格行的上下文菜单，然后选择&#x200B;**[!UICONTROL 比较时间段]**。

   ![已选择比较时段的表行](assets/compare-time.png)

   >[!NOTE]
   >
   >对于量度行、日期范围行和时间维度行，此上下文菜单选项处于禁用状态。

1. 根据您设置表格日期范围的具体方式，您可以使用以下选项进行比较：

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 在此日期范围&#x200B;*之前的*x]**&#x200B;周/月/季度/年 | 与此日期范围之前的选定日期范围进行比较。 |
   | **[!UICONTROL 去年到此日期范围的x周/月/季度/年]** | 与一年前的同一日期范围进行比较。 |
   | **[!UICONTROL 将日期范围自定义为此日期范围]** | 允许您定义自定义日期范围。 |

   >[!NOTE]
   >
   >如果您选择自定义天数，例如 10 月 7 日至 10 月 20 日（14 天范围），您将只获得 2 个选项：**[!UICONTROL 在此日期范围之前的 14 天]**&#x200B;和&#x200B;**[!UICONTROL 将日期范围自定义为此日期范围]**。

1. 得出的比较与下图类似：

   ![显示日期范围和百分比变化比较的自由格式表。](assets/compare-time-result.png)

   “百分比变化”列中的行在负值时显示为红色，在正值时显示为绿色。

## 添加时间段列以进行比较

您现在可以向表中的每一列添加一个时间段，从而添加与日历所设置的时间段不同的时间段。

1. 右键单击表格中的列并选择&#x200B;**[!UICONTROL 添加时间段列]**。

   ![](assets/add-time-period-column.png)

1. 根据您设置表格日期范围的具体方式，您可以使用以下选项进行比较：

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 在此日期范围&#x200B;*之前的*x]**&#x200B;周/月/季度/年 | 添加具有周/月/等的列。 紧邻此日期范围之前。 |
   | **[!UICONTROL 去年至此日期范围的这&#x200B;*x*周/月/季度/年]** | 添加一年前的同一日期范围。 |
   | **[!UICONTROL 将日期范围自定义为此日期范围]** | 允许您创建自定义日期范围。 |

   >[!NOTE]
   >
   >如果您选择自定义天数，例如 10 月 7 日至 10 月 20 日（14 天范围），您将只获得 2 个选项：**[!UICONTROL 在此日期范围之前的 14 天]**&#x200B;和&#x200B;**[!UICONTROL 将日期范围自定义为此日期范围]**。

1. 此时段插入在您选择的列的顶部：

   ![显示当前日历期间和上一个日历月发生情况的自由格式表。](assets/add-time-period-column2.png)

1. 您可以根据需要添加任意数量的时间列，还可以混合和匹配不同的日期范围：

1. 此外，您可以对每个列进行排序，这根据排序所在的列更改天顺序。

## 将列日期调整为从同一行开始

您可以将每列的日期调整为全部从同一行开始。

例如，您会对上周（截至2024年10月5日）和前一周进行逐日比较。 默认情况下，左列将从9月22日开始，右列将从9月29日开始。

![日期不一致](assets/not-align-dates.png)

对于自由格式表可视化图表，您可以在&#x200B;**[!UICONTROL 设置]**&#x200B;中启用[将每列的日期调整为全部从同一行](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1)开始，将列日期调整为从同一行开始。

![](assets/align-dates.png)

使用此选项时，请考虑以下事项：

* 所有新项目均默认启用此设置。

* 此设置适用于整个表格。例如，如果更改表中划分的此设置，则该设置将应用于整个表。


<!--
# Date comparison

Date comparison in Analysis Workspace lets you take any column containing a date range and create a common date comparison, such as: year-over-year, quarter-over-quarter, month-over-month, etc.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Date comparison](https://video.tv.adobe.com/v/33232?quality=12&learn=on&captions=chi_hans){target="_blank"} for a demo video.

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