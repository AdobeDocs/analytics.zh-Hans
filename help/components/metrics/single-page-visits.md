---
title: 单页面访问量
description: “页面”维项目在访问中未更改的次数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 62%

---


# 单页面访问量

*此帮助页面介绍了“单页面访问量”如何作为维度使用。有关更多信息，请参阅[单页面访问量](../dimensions/single-page-visits.md)维度。*

The &#39;Single page visits&#39; metric shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single unique value for the entire visit. 当您想要了解短期访问次数维度，但没有设置如[跳出次数](bounces.md)那么严格的规则时，此量度非常有用。

## 如何计算此量度

此度量计算“页面”维度项目在整个访问中仅包含单个唯一值的访问次数。 如果访客重新加载页面或触发链接跟踪调用，仍将其计为“单个页面访问次数”。“页面”维度一旦变为第二个唯一值，访问就不再计为单个页面访问次数。

请参阅[单次存取](single-access.md)，以了解不同量度之间的比较。
