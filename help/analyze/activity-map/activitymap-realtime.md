---
description: 实时页面分析（实时模式）允许您实时获取带有分钟粒度的结果。
title: 实时页面分析（实时模式）
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 71%

---


# 实时页面分析（实时模式）

实时页面分析（实时模式）允许您实时获取带有分钟粒度的结果。

Activity Map现在以1分钟至15分钟的增量显示分析数据，以根据选定页面的微观趋势监控链接的受欢迎程度。 这对于出版企业跟踪和响应人们对新闻报道的兴趣变化情况以及监控实时流量而言，至关重要。

作为网站内容的所有者，您的一部分工作就是要了解何时推广、何时删除内容，并让我们的体验一直具备相关性。实时数据就是这项职责的命脉。因此，如果您能了解目前最流行的链接和内容，那么您就可以迅速、果断地采取行动，让读者和客户与您的品牌进行互动。

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

如果要检查在实时模式中主要单击的元素：

1. 在工具栏的&#x200B;**[!UICONTROL 实时模式]**&#x200B;趋势线上选择要分析的时间段。
1. 单击工具栏中的“眼睛”图标以访问链接报表表。
1. 通过链接对表进行排序。

## 由 A4T 配置导致的数据滞后

在Adobe Target中启用[A4T集成](https://docs.adobe.com/content/help/zh-Hans/target/using/integrate/a4t/a4t.html)后，Adobe Analytics将再经历5-10分钟的延迟。 这额外增加的滞后允许您将 Analytics 和 Target 中的数据存储到同一个点击上，从而允许您按页面和网站部分来细分测试。

增加的滞后在所有的 Adobe Analytics 服务和工具（包括实时流和实时报表）中都有所体现，且适用于以下情况：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于转化量度的当前数据、最终数据和数据馈送，所有的点击都会额外延迟 5 至 7 分钟的时间。

请注意，实施 [Identity 服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)之后，即使您还未完全实施 A4T 集成，滞后的时间也会开始增加。

更多信息[此处](/help/analyze/activity-map/activitymap-standard-live.md)。