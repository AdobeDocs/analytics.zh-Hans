---
description: 直方图是分析工作区中的一种新的可视化类型。
title: 直方图
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 直方图

直方图与条形图类似，但它将数字分组到范围（桶）中。 Analytics可将数字“分段”自动化到范围中，但您可以在“高级设置”中更 [改设置](#section_09D774C584864D4CA6B5672DC2927477)。

## 构建直方图 {#section_74647707CC984A1CB6D3097F43A30B45}

创建直方图的步骤如下：

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE] 直方图仅支持标准量度，而不支持计算量度。

在此，我们使用了每个唯一视图的页面访客量度。 第一（左）桶对应于每个唯一访客1页视图，第二桶对应于两个页视图等。

![](assets/histogram2.png)

## 高级设置 {#section_09D774C584864D4CA6B5672DC2927477}

要调整直方图设置，请单击右上角的“设置”（“齿轮”）图标。 以下是您可以修改的设置：

| 直方图设置 | 它的用途 |
|---|---|
| 起始存储段 | 确定直方图开始的时段。 “1”是默认值。 可以将起始数从0设置为无限（无负数）。 |
| 量度时段 | 允许您增加／减少数据范围（存储段）的数量。存储段的最大数量为50。 |
| 度量时段大小 | 用于设置每个存储段的大小。 例如，您可以将存储段大小从1页视图更改为2页视图。 |
| 计数方法 | 允许您在 [访客](https://marketing.adobe.com/resources/help/zh_CN/reference/visitors.html)、访 [问](https://marketing.adobe.com/resources/help/zh_CN/reference/metrics_visit.html)或点 [击中](https://marketing.adobe.com/resources/help/zh_CN/reference/hit.html)。 例如，每次访问的页面视图数、每次访客的页面视图数或每次点击的页面视图数。 对于点击来说，“发生次数”可作为自由格式表中的 y 轴量度。 |

**示例**：

* 起始时段：1;量度时段：5;度量时段大小：2将生成此直方图：1-2、3-4、5-6、7-8、9-10。
* 起始时段：0;量度时段：3;度量时段大小：5将生成此直方图：0-4, 5-9, 10-14

## 查看和编辑直方图数据 {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

表格中显示的预置区段是内部区段，将不会在区段选择器中显示。Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

要探索更多用于管理自由格式数据表及其他可视化的方法（如进行数据划分），请转到[此处](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/freeform-analysis-visualizations.html)。
