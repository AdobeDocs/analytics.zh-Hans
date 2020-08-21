---
title: 页面未找到
description: 在您的网站上返回错误的 URL。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 92%

---


# 页面未找到

*此帮助页面介绍“页面未找到”如何作为维度使用。有关详细信息，请参阅[页面未找到](../metrics/pages-not-found.md)量度。*

“页面未找到”维度显示包含错误的 URL。当您希望减少访客在您的网站上收到的错误数时，此维度很有用。

* 您可以在[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)中使用此维度，以查看访客在点击哪些页面时出现错误。然后，您可以与组织中的开发团队合作，修复每个页面上的问题链接。
* 您可以将此维度与[反向链接](referrer.md)维度一起使用，以查看访客从外部链接到达您的网站的哪些位置。然后，您可以实施重定向到所需的位置，或与第三方合作修复链接。

## 使用数据填充此维度

此维度从图像请求中的 [`pageType` 和 `g` 查询字符串](/help/implement/validate/query-parameters.md) 中检索数据。如果 `pageType` 查询字符串等于 `errorPage`，则会记录 `g` 查询字符串（页面 URL）。AppMeasurement 使用 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 变量收集此数据。如果未定义 `pageType` 变量或将其设置为 `errorPage` 之外的任何其他变量，则不会收集此维度的数据。

## Dimension项

Dimension项包括站点上发生错误的页面的URL。
