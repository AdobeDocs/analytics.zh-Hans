---
description: 计算量度和高级计算量度是指您可以从现有量度创建的自定义量度。
keywords: 计算量度；高级计算量度
title: 计算量度和高级计算量度
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: ht
source-wordcount: '552'
ht-degree: 100%

---

# 计算量度和高级计算量度

计算量度和高级计算量度是指您可以从现有量度创建的自定义量度。

我们的计算量度工具提供了一种高度灵活的方式，可用于生成、管理和组织量度。通过使用这些工具，营销人员、产品经理和分析人员不必更改 [!DNL Analytics] 实施，即可提出有关数据的问题。每个 [!DNL Analytics] 包中可用的自定义量度包括：

* Adobe [!DNL Analytics] Foundation：计算量度
* [Adobe Analytics Select](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html)：计算量度 + 高级计算量度
* [Adobe Analytics Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html)：计算量度 + 高级计算量度
* [Adobe Analytics Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html)：计算量度 + 高级计算量度

以下是计算量度和高级计算量度功能的比较：

| Builder 选项 | 计算量度 | 高级计算量度 |
|---|---|---|
| [格式类型（小数、时间、百分比、货币）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | 是 | 是 |
| [归因更改（默认、线性、参与率等）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| [量度类型（标准、总数）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| 基本运算符（加、减、乘、除） | 是 | 是 |
| [应用区段](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | 否 | 是 |
| [基本函数（计数、绝对值、平均值等）](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | 否 | 是 |
| [高级函数（回归、if/then、t 分数等）](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | 否 | 是 |

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 在 [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 异常检测]和 [!UICONTROL 贡献度分析]中创建量度。
* 创建在报告运行时派生的分段量度，而不必更改实施。这些量度可以在历史记录中查看，因为它们是基于区段的。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [计算量度](https://video.tv.adobe.com/v/37926?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

* 在报告包之间共享量度。这表示所有新创建的量度都适用于同一登录公司中的所有报告包。
* （仅限高级计算量度）量度上的区段。例如，您可以为“新访客”创建一个首次进行会话的人员计数的量度。

* （仅限高级计算量度）包含统计函数，以帮助您更好地描述数据。例如，您可以计算报告中的项数，或为每一项添加标准差数字。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [区段中的分段计算量度](https://video.tv.adobe.com/v/37925?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


## 限制 {#section_CB878B02451541D68A68B508D4DBD19A}

某些 [!DNL Analytics] 功能让您可以使用事件，而不是计算量度：

* Analysis Workspace 中的流失
* [!UICONTROL Analysis Workspace 中的队列分析]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 区段]
* [!DNL Analytics] 用于 [!DNL Target]

## 工具 {#section_D65E9C067E9C45E1A50DD30F50561BB2}

以下是 [!UICONTROL 计算量度]工具的简短概述：

| 工具 | 功能 |
|--- |--- |
| 计算量度生成器 | <ul><li>使用高级分配模型创建计算量度和高级计算量度。</li><li>将内联区段添加到量度公式中</li><li>比较同一报告中的区段。例如，比较本地访客与国际访客。</li><li>使用统计函数</li><li>提供详细的量度描述（显示其作用，以及何处可以使用，何处不可以使用）</li><li>将定义复制到新量度中</li><li>提供内联量度预览</li><li>设置量度极性，表示当给定的自定义事件（量度）上升时是有利还是不利</li><li>标记量度</li></ul> |
| 计算量度管理器 | <ul><li>与他人共享量度&lt;/li<li>批准和策划量度</li><li>组织（标记）量度，以便查找</li><li>删除量度</li><li>重命名量度</li></ul> |
| 量度选择器边栏 | 允许您搜索量度，并将量度添加到/应用于报告。您还可以更改排序顺序（选项包括：字母顺序、推荐度、常用性、最近使用。）此外，您可以筛选报告包，以仅显示在某个特定报告包中创建的量度。要访问此“量度选择器”，请点击报告左侧的“量度”图标。 |
| 适用于计算量度的 API | Adobe Analytics 2.0 API 集的组成部分。 |
