---
title: 访问深度
description: 基于访问的维度，用于报告访问的深度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# 访问深度

“访问深度”维度报告访客在整个访问中看到的页面视图数。 仅当点击为页面视图且页面维度与上 [一页](page.md) 视图的维度项不相同时，访问深度才会增加。 它是基于访问的维，这意味着它包含的整个访问的值相同。 该变量针对访问结束后访问中的所有点击设置。

## 用数据填充此维

此维度适用于所有实施。 如果报表包包含数据，则此维有效。

## 维项

维项包括字符串 `"Pages per visit"` 后跟一个数字，表示访问中的页数。 维项表示单 `"Pages per visit: 1"` 页访问，而维项表示具有8页视图 `"Pages per visit: 8"` 的访问（以及任意数量的链接跟踪调用）。

## 与命中深度的比较

有关 [各维之间](hit-depth.md) 的比较，请参阅命中深度。