---
description: Analysis Workspace 中的日期比较允许您采用包含日期范围的任何列来创建常见的日期比较，例如：年同比、季度同比、月同比，等。
title: 日期比较
feature: Calendar
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: ht
source-wordcount: '747'
ht-degree: 100%

---

# 日期比较

Analysis Workspace 中的日期比较允许您采用包含日期范围的任何列来创建常见的日期比较，例如：年同比、季度同比、月同比，等。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [日期比较](https://video.tv.adobe.com/v/33232?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]



## 比较时间段 {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL 比较时间段]会利用高级计算量度。因此，它仅适用于拥有 Analytics Select、Prime 和 Ultimate SKU 的客户。

分析需要上下文，通常这类上下文是由前一时间段提供的。例如，问题“我们比去年同期做得好或差多少？”是了解您的业务的基础。日期比较会自动包含“差异”列，该列显示相较指定时间段的百分比变化。

1. 创建自由格式表，并且在该表中包含您要在一个时间段内比较的任何维度和量度。
1. 右键单击表格行并选择&#x200B;**[!UICONTROL 比较时间段]**。

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >对于量度行、日期范围行和时间维度行，此右键单击选项处于禁用状态。

1. 根据您设置表格日期范围的具体方式，您可以使用以下选项进行比较：

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 在此日期范围之前的周/月/季/年]** | 与周/月/等进行比较。紧邻此日期范围之前。 |
   | **[!UICONTROL 本周/月/季/年/去年至此日期范围]** | 与一年前的同一日期范围进行比较。 |
   | **[!UICONTROL 将日期范围自定义为此日期范围]** | 允许您选择自定义日期范围。 |

   >[!NOTE]
   >
   >如果您选择自定义天数，例如 10 月 7 日至 10 月 20 日（14 天范围），您将只获得 2 个选项：**[!UICONTROL 在此日期范围之前的 14 天]**&#x200B;和&#x200B;**[!UICONTROL 将日期范围自定义为此日期范围]**。

1. 得出的比较与下图类似：

   ![](assets/compare-time-result.png)

   “百分比变化”列中的行在具有负值时显示红色，在具有正值时显示绿色。

1. （可选）与在任何其他 Workspace 项目中一样，您也可以根据这些时间比较创建可视化图表。例如，以下是一个条形图：

   ![](assets/compare-time-barchart.png)

   请注意，为了在条形图中显示百分比变化，您必须在[!UICONTROL 可视化图表设置]中选中[!UICONTROL 百分比]设置。

## 添加时间段列以进行比较 {#section_93CC2B4F48504125BEC104046A32EB93}

现在，您可以向表中的每一列添加一个时间段，此操作允许您添加一个不用于日程表设置的时间段。这是比较日期的另一种方法。

1. 右键单击表格中的列并选择&#x200B;**[!UICONTROL 添加时间段列]**。

   ![](assets/add-time-period-column.png)

1. 根据您设置表格日期范围的具体方式，您可以使用以下选项进行比较：

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 在此日期范围之前的周/月/季/年]** | 添加包含周/月/等的列。紧邻此日期范围之前。 |
   | **[!UICONTROL 本周/月/季/年/去年至此日期范围]** | 添加一年前的同一日期范围。 |
   | **[!UICONTROL 将日期范围自定义为此日期范围]** | 允许您选择自定义日期范围。 |

   >[!NOTE]
   >
   >如果您选择自定义天数，例如 10 月 7 日至 10 月 20 日（14 天范围），您将只获得 2 个选项：**[!UICONTROL 在此日期范围之前的 14 天]**&#x200B;和&#x200B;**[!UICONTROL 将日期范围自定义为此日期范围]**。

1. 时间段将被插入到选定列的顶部：

   ![](assets/add-time-period-column2.png)

1. 您可以根据需要添加任意数量的时间列，还可以混合和匹配不同的日期范围：

   ![](assets/add-time-period-column4.png)

1. 此外，您也可以对每个列进行排序，这将根据排序所依据的列更改日顺序。

## 将列日期调整为从同一行开始 {#section_5085E200082048CB899C3F355062A733}

您可以将每列的日期调整为全部从同一行开始。

例如，如果选择调整日期，并在 2016 年 10 月和 9 月间进行月同比比较，那么左列将从 10 月 1 日开始，右列将从 9 月 1 日开始：

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>使用此选项时，请考虑以下事项：
>
>* 所有新项目均默认启用此设置。
>
>* 此设置适用于整个表格。例如，如果您更改表格内此细分的设置，它将更改整个表格的设置。
>

如果尚未启用此设置，请执行以下操作：

1. 在您想要调整列日期的表格中，选择表格标题中的&#x200B;**设置**&#x200B;图标。

1. 在&#x200B;[!UICONTROL **设置**]&#x200B;选项卡上，选择&#x200B;**[!UICONTROL 将每列的日期调整为全部从同一行开始（适用于整个表）]**。

![](assets/date-comparison-setting.png)


