---
description: 数据插入 API 文档的链接
title: 数据插入 API
feature: API
exl-id: d0ed201a-4bc9-49e2-919b-8cea4fcff587
role: Admin
TQID: 'https://experienceleague.adobe.com/cEsfgydFgbFPowfsyiay6EYWP7S7pjMvqJNcDqfLu9I'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 28%
---
# 数据插入 API

[Data Insertion API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)和[Bulk Data Insertion API](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/)都是将服务器端收集数据提交到Adobe Analytics的方法。 每次生成事件时都将调用“数据插入 API”。 “批量数据插入 API”接受包含事件数据在内的 CSV 格式的文件，其中每行有一个事件。

如果您正在实施新的服务器端收集，Adobe建议使用批量数据插入API。

有关端点、请求和响应格式以及完整的变量引用，请参阅Adobe Developer上的[数据插入API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)和[批量数据插入API](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/)文档。
