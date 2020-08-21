---
title: 点击深度
description: 点击进行访问的次数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 75%

---


# 点击深度

“点击深度”维度报告给定点击访问的深度。此维度对于了解访客在您网站上执行操作的访问深度非常重要。点击深度计算所有类型的点击，包括页面视图 ([`t()`](/help/implement/vars/functions/t-method.md)) 和链接跟踪点击 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## Dimension项

Dimension items include the string `"Hit Depth"` followed by a number representing the number of hits into the visit. The dimension item of `"Hit Depth 1"` represents the first hit of the visit, while the dimension item `"Hit Depth 8"` represents the 8th hit of the visit.

## 与访问深度相比较

点击深度计算所有类型的点击，包括页面视图和链接跟踪点击。Visit depth only increments for page view hits, _and_ the [Page](page.md) dimension item is not the same as the value on the previous page. 访问深度也是一个基于访问的维度，这意味着访问中的所有点击具有相同的值。下表概述了一个访问示例，以及它如何考虑点击深度 + 访问深度：

| 页面序列 | 点击深度 | 是否计入访问深度？ | 访问深度 |
| --- | --- | --- | --- |
| 主页 | 1 | 是 | 4 |
| 产品页 | 2 | 是 | 4 |
| 主页 | 3 | 是 | 4 |
| 自定义链接点击 | 4 | 否（自定义链接） | 4 |
| 自定义链接点击 | 5 | 否（自定义链接） | 4 |
| 产品页 | 6 | 是 | 4 |
| 自定义链接点击 | 7 | 否（自定义链接） | 4 |
| 产品页 | 8 | 否（与上一页相同） | 4 |
