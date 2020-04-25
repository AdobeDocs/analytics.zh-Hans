---
description: 工作区总计的计算方式。
title: 工作区总计
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 工作区总计

在自由格式表中，每个划分级别都显示一个总计行，可以显示两个总计行：

* **[!UICONTROL Grand Total]** （灰色“out of”数字）-此总数表示已收集的所有点击，有时称为“报表包总数”。 当在面板级别或自由格式表中应用区段时，此总计会进行相应的调整以反映符合区段标准的所有点击。
* **[!UICONTROL Table Total]** （黑色数字）-此总数通常等于或是子集 [!UICONTROL Grand Total]。 It reflects any table filters applied within the freeform table, including the [!UICONTROL Include None] option.

![](assets/total-row.png)

## 显示总计设置

在 **[!UICONTROL Column Settings]**&#x200B;下面，可选择和 **[!UICONTROL Show Totals]** 选择 **[!UICONTROL Show Grand Total]**。 如果未选中这些设置，则将从表中删除总计。当总计不合理（例如，在某些[计算量度](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)场景中）时，可能需要此操作。

![](assets/column-settings-total.png)

## 静态行总计设置

[静态行合计](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) ，其行为方式不同，并且受控制 **[!UICONTROL Row Settings]**。

* **[!UICONTROL Show sum of current rows as the total]** -这显示表中各行的客户端总和，这意味着总和不会 **重复** (如访问或访客)。
* **[!UICONTROL Show Grand Total]** -这显示服务器端总和，即访问量或访客等总计将减少重复量度。

![](assets/static-rows.png)

## 常见问题解答

| 问题 | 回答 |
|---|---|
| 灰色列百分比基于哪个“总计”？ | 这取决于以下项 **[!UICONTROL Percentages]** 下的设置选择 **[!UICONTROL Row Settings]**:<ul><li>按列计算百分比 - 这是默认设置。百分比将基于表总数。</li><li>按行计算百分比 - 百分比将基于总计。</li></ul> |
| 设置对总体 **[!UICONTROL Include Unspecified (None)]** 有何影响？ | If the **[!UICONTROL Include Unspecified (None)]** setting is unchecked, the None/Unspecified row will be removed from the table, the Table Total, and will carry through to any calculated metrics that use [&#39;Total&#39; metric types](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| 将自定义表过滤器应用于自由格式表后，我的所有计算量度和条件格式是否都将过滤器考虑在内？ | 当前不是。**[!UICONTROL Include Unspecified (None)]** 将被计入，但自定义表过滤器不会影响以下内容：<ul><li>条件格式使用的列最大/最小范围将分析所有数据。</li><li>利用度量类型的计 **[!UICONTROL Grand Total]** 算度量。</li><li>使用函数计算自由格式表中各行的计算度量 - 即，列总和、列最大值、列最小值、计数、平均值、中间值、百分位数、四分位数、行计数、标准偏差、方差、累积、累积平均值、回归变量、T 分数、T 检验、Z 分数、Z 检验。</li></ul> |
| In Calculated Metrics, what does the **[!UICONTROL Grand Total]** metric type reflect? | **[!UICONTROL Grand Total]** 继续引用， **[!UICONTROL Grand Total]**&#x200B;但不反映应用于表或表的过滤器 **[!UICONTROL Table Total]**。 |
| 从自由格式表复制和粘贴数据或通过 CSV 下载数据时，显示的总计是多少？ | 总行将仅反映列 **[!UICONTROL Table Total]** 设置，并且尊重列 **[!UICONTROL Show Totals]** 设置。 |

