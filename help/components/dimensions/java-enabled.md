---
title: 已启用 Java
description: 确定浏览器中是否已启用 Java。
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 93%

---

# 已启用 Java

“已启用Java”[维度](overview.md)确定当时浏览器是否启用了Java。 如果您要在网站上引入基于 Java 的功能，并且想知道有多少访客已经启用 Java，则此功能非常有用。 对于已禁用 Java 的访客，您可以提供替代方案或关于如何启用 Java 的操作说明。

## 使用数据填充此维度

此维度从图像请求中的 [`v` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。 AppMeasurement 通过检测浏览器中是否已启用 Java 来收集此数据。 如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。 如果您使用 AppMeasurement 之外的数据收集方法（例如，通过 API），请确保包括 `v` 查询字符串参数，其中包含“Y”或“N”值（如果您希望使用此维度的话）。

## 维度项目

维度项目包括“已启用”、“已禁用”和“未知”。

* **已启用**：浏览器中已启用 Java。 `v` 查询字符串包含“Y”值。
* **已禁用**：浏览器中已禁用 Java，或者不支持 Java。 `v` 查询字符串包含“N”值。
* **未知**：AppMeasurement 无法确定是否支持 Java。 图像请求中不存在 `v` 查询字符串。
