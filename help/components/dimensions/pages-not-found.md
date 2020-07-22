---
title: 页面未找到
description: 在您的站点上返回错误的URL。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# 页面未找到

*此帮助页介绍“找不到页面”作为维的工作方式。 有关详细[信息，请参阅](../metrics/pages-not-found.md)“找不到页面”度量。*

“找不到页面”维显示包含错误的URL。 当您希望减少访客在您的站点上收到的错误数时，此维度很有用。

* 您可以在流可视化中使 [用此维](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) 度，查看访客点击哪些页面以查看错误。 然后，您可以与组织中的开发团队合作，修复每个页面上的链接。
* 您可以将此维与“推荐人 [”维一起使](referrer.md) 用，以查看访客从外部链接到达您的站点的位置。 然后，您可以实施重定向到所需的位置，或与第三方合作修复链接。

## 用数据填充此维

此维从图像请求中的数 [`pageType` 据和 `g` 查询字符串](/help/implement/validate/query-parameters.md) 中检索数据。 如果 `pageType` 查询字符串 `errorPage`等于，则 `g` 会记录查询字符串（页面URL）。 AppMeasurement使用变量收集此 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 数据。 如果未 `pageType` 定义变量或将其设置为除 `errorPage`外的任何其他变量，则不会收集此维的数据。

## 维项

维项目包括站点上发生错误的页面的URL。
