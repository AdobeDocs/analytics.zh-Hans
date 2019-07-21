---
description: 实时页面分析（实时模式）允许您实时获取带有分钟粒度的结果。
seo-description: 实时页面分析（实时模式）允许您实时获取带有分钟粒度的结果。
seo-title: 实时(实时)页面分析
solution: Analytics
title: 实时(实时)页面分析
topic: Activity Map
uuid: a faa9bd-73d8-48b3be3b-f818 edd7456 fb
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 实时(实时)页面分析

实时页面分析（实时模式）允许您实时获取带有分钟粒度的结果。

Activity Map 现在以 1 至 15 分钟的时间增量为间隔，来显示分析数据，以便根据选定页面的微观趋势来监控链接的受欢迎程度。这对于出版企业跟踪和响应人们对新闻报道的兴趣变化情况以及监控实时流量而言，至关重要。

作为网站内容的所有者，您的一部分工作就是要了解何时推广、何时删除内容，并让我们的体验一直具备相关性。实时数据就是这项职责的命脉。因此，如果您能了解目前最流行的链接和内容，那么您就可以迅速、果断地采取行动，让读者和客户与您的品牌进行互动。

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Data latency as a result of A4T configuration {#section_806CE36354FC4C539A0DED9266A5C704}

在 Adobe Target 中启用 A4T 集成后，您在 Adobe Analytics 中会额外经历 5 至 10 分钟的滞后。这额外增加的滞后允许您将 Analytics 和 Target 中的数据存储到同一个点击上，从而允许您按页面和网站部分来细分测试。

增加的滞后在所有的 Adobe Analytics 服务和工具（包括实时流和实时报表）中都有所体现，且适用于以下情况：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于转化量度的当前数据、最终数据和数据馈送，所有的点击都会额外延迟 5 至 7 分钟的时间。

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
