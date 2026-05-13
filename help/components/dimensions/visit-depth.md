---
title: 访问深度
description: 报告访问深度的基于访问的维度。
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 90%

---

# 访问深度

“访问深度”[维度](overview.md)报告访客在整个访问中查看的页面查看次数。 仅当点击为页面查看，且[页面](page.md)维度与最后页面查看的维度项目不同时，访问深度才会增加。 它是一个基于访问的维度，这意味着它在整个访问期间包含的值是相同的。 该变量针对访问结束后访问中的所有点击设置。

## 使用数据填充此维度

此维度可开箱即用于所有实施。 如果报表包包含数据，则此维度有效。

## 维度项目

维度项目包括字符串 `"Pages per visit"`，后跟一个数字，表示访问的页面数量。 维度项目 `"Pages per visit: 1"` 表示单页访问，而维度项目 `"Pages per visit: 8"` 表示具有 8 次页面查看（以及任意数量的链接跟踪调用）的访问。

## 与点击深度进行比较

请参阅[点击深度](hit-depth.md)，了解维度之间的比较情况。
