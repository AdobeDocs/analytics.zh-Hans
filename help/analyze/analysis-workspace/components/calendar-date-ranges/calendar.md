---
description: 在日程表中，您可以指定日期和日期范围，或者选择一个预设。
title: 日程表和日期范围概述
feature: Calendar
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: ht
source-wordcount: '942'
ht-degree: 100%

---

# 日程表和日期范围概述 {#date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="结束时间"
>abstract="结束时间始终包括 59 秒。"

<!-- markdownlint-enable MD034 -->


在日程表中，您可以指定日期和日期范围，或者选择一个预设。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [日程表和日期范围概述](https://video.tv.adobe.com/v/328022?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


日程表选择在面板级别应用，但您可以选择将它们应用于所有面板。 在 Workspace 中单击日期范围时，界面将显示当前日程表月和上一个日程表月。您可以通过单击上方左右边角的左右箭头来调整这两个日程表。

![日程表](assets/aw_calendar2.png){width="60%"}

## 选择并应用日期范围 {#select-apply}

第一次单击日程表将开始日期范围选择。第二次单击将完成日期范围选择，所选的日期范围将突出显示。如果按下 `Shift` 键（或使用右键单击），则会附加到当前选定的范围。

您还可以将日期（和时间维度）拖放到 Workspace 项目中。您可以选择特定的日期、周、月、年或滚动日期。

[在 Analysis Workspace 中使用日期范围和日程表](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=zh-hans) (4:07)

| 设置 | 描述 |
|--- |--- |
| 选定的日期 | 选定的日期/周/月/年。 |
| 使日期范围组件相对于面板日程表 | 如果禁用，表格、可视化图表或面板下拉区域中使用的任何日期范围组件都会覆盖面板日程表。 <p>如果启用，表格、可视化图表或面板下拉区域中使用的任何日期范围组件都与面板日期范围相关。例如，如果面板日期范围设置为 11 月 1 日至 11 月 30 日，并且在自由格式表中使用了上周日期范围组件，则自由格式表中的信息指的是 10 月的最后一周。 |
| 使用滚动日期 | 滚动日期允许您生成一个动态报告，从而可根据您运行报告的时间向前或向后查看一段特定的时间段。例如，如果您要报告“上个月”安排的所有订单（基于“创建日期”字段）并在十二月运行该报告，则会看到十一月安排的订单。如果您在一月运行同一报告，则会看到十二月安排的订单。<ul><li>**[!UICONTROL 日期预览]**：指示滚动日程表包含哪些时间段。</li><li>**[!UICONTROL 开始]**：您可以在当天、当周、当月、当季、当年之间进行选择。</li><li>**[!UICONTROL 结束]**：您可以在当天、当周、当月、当季、当年之间进行选择。</li></ul>要查看示例，请参阅[自定义日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md)。 <br>默认选定。 |
| 日期范围 | 您可以选择一个预设日期范围。最近 30 天为默认设置。**[!UICONTROL 本周/月/季度/年（不包括今天）]**&#x200B;允许您从不包括今天的部分日期数据的日期范围中进行选择。 |
| 应用于所有面板 | 您不仅可以更改当前面板的选定日期范围，还会更改项目内所有其他面板的日期范围。 |
| 应用 | 将日期范围仅应用于此面板。 |

## 关于相对面板日期范围 {#relative-panel-dates}

如果您在使用 Workspace，则可以使日期范围组件相对于面板日程表。
您最常见的三种相对面板日期生效用例包括组合图表、关键量度摘要和自由格式表格日期范围。

要使用相对面板日期范围

1. 选择 **Workspace** 选项卡。
1. 选择&#x200B;**空白项目**。
1. 从左边栏添加维度、度量和区段。
1. 单击面板日期范围字段，切换相对面板日期范围设置。
1. 选择&#x200B;**使日期范围组件相对于面板日程表**。
   * 选择使日期范围组件与面板日程表相对的选项。如果选择相对日期，则滚动日期将以面板日程表的开始日期而非今天日期为准。
   * 如果未选择此选项，则滚动日期将以今天日期为准。

   ![相对面板日期](assets/relative-date-selected.png){width="60%"}

1. 单击&#x200B;**应用**。相对日期显示在右上角。

   ![自由格式的相对日期 ](assets/relative-date-range1.png)

## 相对面板日期范围准则 {#guidelines}

使用相对面板日期范围时，请牢记以下准则。

### 公式和相对日期范围 {#formula-relative-dates}

如果您选择了相对日期，则所有日期公式都将使用面板的开始日期作为起点。

### 自定义日程表和相关日期范围 {#custom-calendar-formulas}

当您使用基于周的自定义日程表并添加月份或年份时，该公式会计算给定时间段中日偏移量。由于会出现偏移，实际日期可能会有所不同。该公式会选择落在自定义日程表中同一位置的日期。例如，自定义日程表中第三周的第三个星期五。

### 关于使用滚动日期和相对面板日期范围的区段 {#segments-relative-dates}

如果您生成区段或使用具有滚动日期的区段，例如，过去 7 天或过去 2 周，并单击区段预览，系统将会从&#x200B;*今天*&#x200B;开始滚动日期而非从面板开始日期滚动。因此，当您实际使用表中的区段时，区段的预览将会不相符。受影响的是预览，而非区段本身。

## 有关面板日期范围和预览的准则 {#guidelines-panel-dates}

* 从 2 月版开始，组件和数据预览将基于面板日期范围，而不是过去 90 天。
* 是否有左侧边栏中列出的所有组件可用，取决于面板日期范围。
* 区段和计算度量生成器中的所有日期预览都将基于面板日期范围（除非从组件管理器访问，这样没有的关联面板，它们仍将基于过去 90 天）。
* 任何数据预览都将根据面板日期范围显示数据或组件。