---
title: 访问深度
description: 报告访问深度的基于访问的维度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 57%

---


# 访问深度

“访问深度”维度报告访客在整个访问中查看的页面查看数量。Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view&#39;s dimension item. 它是一个基于访问的维度，这意味着它在整个访问期间包含的值是相同的。该变量针对访问结束后访问中的所有点击设置。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## Dimension项

Dimension items include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension item of `"Pages per visit: 1"` represents a single-page visit, while the dimension item `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## 与点击深度进行比较

请参阅[点击深度](hit-depth.md)，了解维度之间的比较情况。