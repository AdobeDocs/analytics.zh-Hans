---
description: 了解如何将成本和预算金额分配给渠道。
seo-description: 了解如何将成本和预算金额分配给渠道。
seo-title: 成本和预算
solution: Analytics
subtopic: 营销渠道
title: 成本和预算
topic: Reports and Analytics
uuid: 7ba0e968-e565-4d4c-8fc0-39bf25d3e5b1
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 成本和预算

了解如何将成本和预算金额分配给渠道。

成本表示您在渠道上的花费。预算表示可用的花费金额。

查看投资回报率的有效方法是创建一个显示收入与成本差额的计算量度。或者，也可以创建一个显示总成本连同每一项新参与成本明细情况的计算量度。例如，您可以运行显示新参与的[!UICONTROL “首次联系渠道”]报表。然后，通过创建计算量度，添加“首次联系成本”量度，显示每一项新参与的成本。

请参阅 [营销渠道报表中使用的计算量度](/help/components/c-marketing-channels/c-channel-calc-metrics.md).

您可以将成本和预算仅分配到渠道。所有成本都有指定的时间范围，在此时间范围内它们将应用到报表中。当成本和渠道直接关联时，则会选择分配量度来显示渠道内成本在各营销活动中是如何划分的。

在添加成本和预算项目后，您可以将表格数据导出到 CSV 文件中。您也可以将 CSV 文件导入到“营销渠道成本”页面。

## 添加成本和预算项目 {#add-cost-and-budget}

向营销渠道中添加成本和预算项目。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. 在[!UICONTROL “报表包管理器”]页面上，选择一个报表包。
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Costs]**.
1. On the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Add Cost Item]** or **[!UICONTROL Add Budget Item]**.
1. Click **[!UICONTROL Save.]**

   To continue adding cost items, click **[!UICONTROL Save and Add Another]**.

1. (Optional) To export or import CSV files, access the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Export File]** or **[!UICONTROL Import File]**, then follow the prompts.

## Marketing Channel costs - definitions {#mktg-channel-costs}

“营销渠道成本”或“营销渠道预算”的字段定义。

| 字段 | 定义 |
|--- |--- |
| 名称 | 成本或预算项目的名称。（如果您正在使用 SAINT，此值为关键值。） |
| 渠道 | 您要将这笔金额关联到的渠道。指定成本或预算是否应用于首次联系渠道或最近联系渠道。将首次联系成本金额视为一个一次性的新参与。最近联系成本金额用于点进次数。 |
| 日期范围 | 您要使用这笔金额的时段。 |
| 类型 | 成本或预算的类型：“费用”或“一次成本”。“费用”指定持续的成本，例如每次点击的金额。“一次成本”可让您指定“分发者”金额。例如，如果您通过点击量分配成本，60％ 的总点击量则归于 60％ 的总成本。分发者值就是您在划分数字分类时所采用的量度。 |
| 导出文件 | 您可以将表格数据导出为 CSV 文件。 |
| 导入文件 | 您可以将 CSV 文件导入到“营销渠道成本”页面。 |
