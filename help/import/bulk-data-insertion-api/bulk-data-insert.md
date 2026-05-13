---
title: 批量数据插入 API
description: 批量数据插入API (BDIA)是一种Adobe Analytics功能，允许您以文件的形式批量上传服务器调用数据，而不是使用客户端库（如AppMeasurement）。
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 85%

---

# 批量数据插入 API

批量数据插入解决数个用例，比如：

* 从以前的 Analytics 系统中提取历史数据

* 内部 Analytics 收集系统，无法使用 AppMeasurement。 您可以使用提取 - 转换 - 加载（ETL）过程将数据放入批处理文件，然后使用 BDIA 将其上载到 Adobe Analytics。

* 从只能断断续续连接到网络的设备收集数据。 这些设备存储交互数据，直到接收网络连接。 然后，设备可以通过 BDIA 一次上传所有数据。

数据插入 API 和[ 批量数据插入 API ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)是将服务器端收集的数据提交到 Adobe Analytics 的两种方式。 每次生成事件时都将调用“数据插入 API”。 “批量数据插入 API”接受包含事件数据在内的 CSV 格式的文件，其中每行有一个事件。 如果您正在实施新的服务器端收集，我们建议您使用“批量数据插入 API”。
