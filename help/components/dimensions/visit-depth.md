---
title: 访问深度
description: 报告访问深度的基于访问的维度。
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 89%

---

# 访问深度

“访问深度”[维度](overview.md)报告访客在整个访问中查看的页面查看次数。 仅当点击为页面查看，且[页面](page.md)维度与最后页面查看的维度项目不同时，访问深度才会增加。它是一个基于访问的维度，这意味着它在整个访问期间包含的值是相同的。该变量针对访问结束后访问中的所有点击设置。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## 维度项目

维度项目包括字符串 `"Pages per visit"`，后跟一个数字，表示访问的页面数量。维度项目 `"Pages per visit: 1"` 表示单页访问，而维度项目 `"Pages per visit: 8"` 表示具有 8 次页面查看（以及任意数量的链接跟踪调用）的访问。

## 与点击深度进行比较

请参阅[点击深度](hit-depth.md)，了解维度之间的比较情况。
