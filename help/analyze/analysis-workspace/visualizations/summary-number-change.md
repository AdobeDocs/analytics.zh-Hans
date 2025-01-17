---
description: 使用“概要数字”和“概要变化”可视化图表来显示项目中的重要数据点。
title: 概要数字和概要变化
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 93%

---

# [!UICONTROL 概要数字]和[!UICONTROL 概要变化]

*本文记录了&#x200B;**Adobe Analytics**中的摘要编号和摘要更改可视化图表。<br/>查看本文的&#x200B;**Customer Journey Analytics**版本的[摘要编号和摘要更改](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change)。*

以下是一段关于这两个可视化图表的视频：

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL 概要数字]可视化图表 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="摘要数字"
>abstract="创建显示总计和小计的可视化效果。"

<!-- markdownlint-enable MD034 -->

使用[!UICONTROL 概要数字]可视化图表来突出显示项目中的大型重要数字。 此可视化图表的行为方式如下：

* 如果未选中单元格，此可视化则会选择总列数。
* 如果选中了单个单元格，此可视化则会显示该单元格的概要。
* 如果选中了多个单元格，此可视化则会显示所选单元格的第一个单元格。
* 如果选中了列，此可视化则会选择列中的第一个单元格值。

单击右上方的&#x200B;**可视化设置**&#x200B;齿轮，可配置“概要数字”设置：

| 设置 | 定义 |
|--- |--- |
| [!UICONTROL 百分比] | 显示百分比，而不是原始数字。 |
| [!UICONTROL 图例可见] | 显示有关所显示的量度的信息。 |
| [!UICONTROL 缩写值] | 选择缩写值，最多显示 3 个小数位。 |
| [!UICONTROL 值汇总方式] | 选择显示所选数据的最大值、最小值、平均值、中间值或总和。 |

## [!UICONTROL 概要变化]可视化图表 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="概要变化"
>abstract="创建一个显示两个数字之间增量（变化）的可视化图表"

<!-- markdownlint-enable MD034 -->

使用[!UICONTROL 概要变化]可视化图表来显示两个数字之间的增量（变化）。 可通过[自定义事件极性](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)或计算量度的[将上升趋势显示为](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=zh-Hans)选项来控制[!UICONTROL 概要变化]的绿色和红色。

此可视化图表的行为方式如下：

* 如果未选中单元格，此可视化会比较列中的前两个单元格值。
* 如果选中了一个单元格，此可视化会显示 0，因为它将单元格值与其自身进行比较。
* 如果选中了两个单元格，则第一个选定的单元格将作为分子，第二个单元格将作为分母。
* 如果选中了两个以上的单元格，则会仅考虑比较前两个单元格。
* 如果选中了单元格范围，则会将范围内选定的第一个单元格与最后一个单元格进行比较。
* 如果选中了列，会将第一个值与其自身进行比较，结果会显示变化为 0。


![](assets/summary-change.png)


单击右上方的&#x200B;**可视化设置**&#x200B;齿轮，可配置“概要变化”设置：

| 设置 | 定义 |
| --- | --- |
| [!UICONTROL 百分比] | 显示百分比，而不是原始数字。 |
| [!UICONTROL 图例可见] | 显示有关所显示的量度的信息。 |
| [!UICONTROL 显示百分比变化] | 显示 2 个数字之间的百分比变化。 |
| [!UICONTROL 显示原始差异] | 显示 2 个数字之间的原始差异。您还可以对此选项使用缩写值，并最多显示 3 个小数位。 |
