---
description: 直方图是 Analysis Workspace 中一种新的可视化类型。
title: 直方图
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 90%

---

# 直方图 {#histogram}

arkdownlint-disable MD034 —>

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="直方图"
>abstract="创建可视化直方图来表示范围组中数值数据的分布。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的直方图可视化图表。_<br/>_查看本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[直方图](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/histogram)。_

>[!ENDSHADEBOX]


直方图类似于条形图，不过它可以将数字归为几组不同的范围（存储段）。Analytics 将数字的“存储”自动归为不同的范围，但您可以在[高级设置](#section_09D774C584864D4CA6B5672DC2927477)中更改相关设置。

以下是一段关于如何使用直方图的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23725/?quality=12)

## 构建直方图 {#section_74647707CC984A1CB6D3097F43A30B45}

创建直方图的步骤如下：

1. 单击左边栏中的&#x200B;**[!UICONTROL 可视化]**。
1. 将&#x200B;**[!UICONTROL 直方图]**&#x200B;拖到面板中。
1. 选择要拖到直方图可视化中的量度，并单击&#x200B;**[!UICONTROL 生成]**。

![](assets/histogram.png)

>[!NOTE]
>
>直方图仅支持标准量度，而不支持计算量度。

这里我们使用的是对应每个独特访客的页面查看次数量度。第一个（左）存储段对应每个独特访客 1 次页面查看，第二个存储段对应 2 次页面查看，依次类推。

![](assets/histogram2.png)

## 高级设置 {#section_09D774C584864D4CA6B5672DC2927477}

要调整直方图设置，请单击右上角的“设置”（齿轮）图标。以下是可修改的设置：

| 直方图设置 | 它的功能 |
|---|---|
| 开始存储段 | 确定直方图从哪个存储段开始。“1”为默认值。您可以在 0 到无穷大（非负数）的范围内设置开始数量。 |
| 量度存储段 | 允许您增加/减少数据范围（存储段）的数量。 存储段的最大数量为50。 |
| 量度存储段大小 | 您可以设置每个存储段的大小。例如，您可以将存储段大小从 1 次页面查看更改为 2 次页面查看。 |
| 计算方法 | 您可以在[访客](/help/components/metrics/unique-visitors.md)、[访问](/help/components/metrics/visits.md)或[点击类型](/help/components/dimensions/hit-type.md)中进行选择。例如，每次访问的页面查看次数或每位访客的页面查看次数，或者每次点击的页面查看次数。对于点击来说，“发生次数”可作为自由格式表中的 y 轴量度。 |

<!--Russ or Meike - Check Hit Type link above. -->

**示例**：

* 开始存储段：1；量度存储段：5；量度存储段大小：2 将生成此直方图：1-2、3-4、5-6、7-8、9-10。
* 开始存储段：0；量度存储段：3；量度存储段大小：5 将生成此直方图：0-4、5-9、10-14。

## 查看和编辑直方图数据 {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

要查看或更改直方图图表的数据源，请单击直方图标题旁边的点，以转到&#x200B;**[!UICONTROL 数据源设置]** > **[!UICONTROL 显示数据源]**。

![](assets/manage-data-source.png)

表格中显示的预置区段是内部区段，将不会在区段选择器中显示。单击区段名称旁边的“i”图标，然后单击&#x200B;**[!UICONTROL 设为公用]**&#x200B;以将区段设为公用。

![](assets/prebuilt_segments.png)

要探索更多用于管理自由格式数据表及其他可视化的方法（如进行数据划分），请转到[此处](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hans)。
