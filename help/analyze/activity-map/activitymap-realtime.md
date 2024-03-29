---
description: 实时页面分析（实时模式）允许您实时获取带有分钟粒度的结果。
title: 实时页面分析（实时模式）
feature: Activity Map
role: User, Admin
exl-id: 29ccd89e-d82b-41d4-a940-addc6656b5ec
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 72%

---

# 实时页面分析（实时模式）

实时页面分析（实时模式）允许您实时获取带有分钟粒度的结果。

Activity Map现在以1分钟到15分钟为增量显示分析数据，以根据选定页面的微趋势监控链接人气。 这对于出版企业跟踪和响应人们对新闻报道的兴趣变化情况以及监控实时流量而言，至关重要。

作为网站内容的所有者，您的一部分工作就是要了解何时推广、何时删除内容，并让我们的体验一直具备相关性。实时数据就是这项职责的命脉。因此，如果您能了解目前最流行的链接和内容，那么您就可以迅速、果断地采取行动，让读者和客户与您的品牌进行互动。

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

如果要检查在实时模式下单击的元素最多，请执行以下操作：

1. 在工具栏的 **[!UICONTROL 实时模式]** 要分析的趋势线。
1. 单击工具栏中的“眼睛”图标以访问“链接报表”表格。
1. 按链接对表进行排序。

## 由 A4T 配置导致的数据滞后

在 [A4T集成](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) 在Adobe Target中启用，则在Adobe Analytics中会额外经历5至10分钟的延迟。 这额外增加的滞后允许您将 Analytics 和 Target 中的数据存储到同一个点击上，从而允许您按页面和网站部分来细分测试。

增加的滞后在所有的 Adobe Analytics 服务和工具（包括实时流和实时报表）中都有所体现，且适用于以下情况：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于转化量度的当前数据、最终数据和数据馈送，所有的点击都会额外延迟 5 至 7 分钟的时间。

请注意，实施 [Identity 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)之后，即使您还未完全实施 A4T 集成，滞后的时间也会开始增加。

更多信息 [此处](/help/analyze/activity-map/activitymap-standard-live.md).
