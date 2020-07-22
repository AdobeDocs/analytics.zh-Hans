---
title: 页面
description: 页面名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# 页面

“页面”维列表站点上的页面名称。 它是AdobeAnalytics中最常用的维度之一，因为它可让您深入了解网站上哪些页面的效果最佳。

此维与“站点”部 [分和服务器](site-section.md)[维相关](server.md) 。 页面粒度最细，服务器粒度最细，站点部分介于两者之间。

## 用数据填充此维

此维从图像请求中的 [`pageName` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用变量收集此 `pageName` 数据。 如果 `pageName` 未定义变量，则返回到使用页面的URL。

## 维项

维项目包括站点上页面的名称。 您的组织确定要使用哪些特定维项目。 一些组织直接使 `document.title`用，而另一些组织则制定自定义痕迹导航。 无论您使用何种方法，都应确保其一致性，并将其记录在解决方案 [设计文档中](/help/implement/prepare/solution-design.md)。

>[!NOTE]
>
>在报告和Analytics中，转化量度使用此维度的线性归因。 For example, revenue is split between all pages viewed in a visit before a `purchase` event. Analysis Workspace默认使用上一个归因，并可选择使用任何归因模型。
