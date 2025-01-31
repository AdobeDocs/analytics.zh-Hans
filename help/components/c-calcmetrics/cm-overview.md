---
description: 计算量度和高级计算量度是指您可以从现有量度创建的自定义量度。
keywords: 计算指标；高级计算指标
title: 计算量度和高级计算量度
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 53%

---

# 计算量度和高级计算量度

计算量度和高级计算量度是指您可以从现有量度创建的自定义量度。

我们的计算指标工具提供了一种高度灵活的方式，可用于生成、管理和组织指标。通过使用这些工具，营销人员、产品经理和分析人员不必更改 [!DNL Analytics] 实施，即可提出有关数据的问题。每个 [!DNL Analytics] 包中可用的自定义指标包括：

* Adobe [!DNL Analytics] Foundation：计算指标
* [Adobe Analytics Select](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html)：计算指标 + 高级计算指标
* [Adobe Analytics Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html)：计算指标 + 高级计算指标
* [Adobe Analytics Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html)：计算指标 + 高级计算指标

以下是计算指标和高级计算指标功能的比较：

| Builder 选项 | 计算量度 | 高级计算量度 |
|---|---|---|
| [格式类型（小数、时间、百分比、货币）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | 是 | 是 |
| [归因更改（默认、线性、参与率等）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| [指标类型（标准、总数）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| 基本运算符（加、减、乘、除） | 是 | 是 |
| [应用区段](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | 否 | 是 |
| [基本函数（计数、绝对值、平均值等）](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | 否 | 是 |
| [高级函数（回归、if/then、t 分数等）](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | 否 | 是 |

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 创建跨[!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 异常检测]和[!UICONTROL 贡献分析]的指标。
* 创建在报表运行时派生的分段量度，而不必更改实施。 这些指标可以在历史记录中查看，因为它们是基于区段的。


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [计算量度](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

* 在报表包之间共享指标。这表示所有新创建的指标都适用于同一登录公司中的所有报表包。
* （仅限高级计算量度）按量度进行分段。 例如，您可以为“新访客”创建一个指标，其中包含首次进行会话的人员计数。

* （仅限高级计算指标）包含统计函数以帮助您更好地描述数据。 例如，您可以对报表中的项目数量进行计数，或为每个项目加入标准偏差数。


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg)[区段中的分段计算量度](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 限制 {#section_CB878B02451541D68A68B508D4DBD19A}

某些 [!DNL Analytics] 功能让您可以使用事件，而不是计算指标：

* Analysis Workspace 中的流失
* [!UICONTROL Analysis Workspace 中的队列分析]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 区段]
* [!DNL Analytics] for [!DNL Target]

## 工具 {#section_D65E9C067E9C45E1A50DD30F50561BB2}

以下是[!UICONTROL 计算量度]工具的简短概述：

| 工具 | 功能 |
|--- |--- |
| 计算量度生成器 | <ul><li>使用高级分配模型创建计算量度和高级计算量度。</li><li>将内联区段添加到量度公式中</li><li>比较同一报表中的区段。例如，比较本地访客与国际访客。</li><li>使用统计函数</li><li>提供详细的量度描述（显示其用途，以及何处可以使用，何处不可以使用）</li><li>将定义复制到新量度中</li><li>提供内联量度预览</li><li>设置量度极性，以指示当给定的自定义事件（量度）上升时是有利还是不利</li><li>标记量度</li></ul> |
| 计算度量管理器 | <ul><li>与他人共享指标&lt;/li<li>批准和管理指标</li><li>组织（标记）量度，以便用户查找</li><li>删除量度</li><li>重命名量度</li></ul> |
| 指标选择器边栏 | 允许您搜索指标，并将指标添加/应用于报表。 您还可以更改排序顺序（选项包括：“按字母顺序”、“推荐”、“经常使用”、“最近使用”。） 此外，您还可以对报表包进行过滤，以仅显示特定报表包中创建的量度。  要访问此指标选择器，请单击报表左侧的“指标”图标。 |
| 适用于计算量度的 API | Adobe Analytics 2.0 API 集的组成部分。 |
