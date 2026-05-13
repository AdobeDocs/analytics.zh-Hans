---
title: 访问量
description: 访客的第 n 次访问。
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
TQID: https://experienceleague.adobe.com/C6fccfJFGSA4iLuhp2X80aPym4ZcwbrLMaUS2LUfosg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 100%

---

# 访问量

“访问量”[维度](overview.md)报告访客当前是第几次访问。 当新访问开始时，此维度项目增加 1。 如果您想了解访客在返回您的网站时的参与程度，此维度很有用。 它是一个基于访问的维度，这意味着它在整个访问期间包含的值是相同的，并且无法更改。 它适用于访客的存留期，而不管项目日期范围如何。

## 使用数据填充此维度

此维度可开箱即用于所有实施。 如果报表包包含数据，则此维度有效。

## 维度项目

维度项目包括字符串 `"Visit number"`，后跟一个数字，表示访客当前正在进行的访问。 例如，如果访客以前从未访问过您的网站，则其首次访问属于维度项目 `"Visit number 1"`。 如果这是访客第 13 次访问您的网站，则属于维度项目 `"Visit number 13"`。
