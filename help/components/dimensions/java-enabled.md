---
title: 已启用 Java
description: 确定浏览器中是否已启用 Java。
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 51%
---
# 已启用 Java

“已启用Java”[维度](overview.md)确定当时浏览器是否启用了Java。 如果您要在网站上引入基于 Java 的功能，并且想知道有多少访客已经启用 Java，则此功能非常有用。 对于已禁用 Java 的访客，您可以提供替代方案或关于如何启用 Java 的操作说明。

## 使用数据填充此维度

自动收集已启用Java的客户端文件： AppMeasurement会检测浏览器中是否已启用Java并报告“Y”或“N”。 它可以在任何AppMeasurement或Web SDK（标记）实施中开箱即用 — 没有要设置的变量。 如果您在AppMeasurement或Web SDK之外（例如通过API）收集数据，请发送“Y”或“N”以使用此维度。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（自动收集） |
| **Web SDK / XDM字段** | 无（自动收集） |
| **查询参数** | [`v`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<javaEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 1字节 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括“已启用”、“已禁用”和“未知”。

* **已启用**：浏览器中已启用 Java。 `v` 查询字符串包含“Y”值。
* **已禁用**：浏览器中已禁用 Java，或者不支持 Java。 `v` 查询字符串包含“N”值。
* **未知**：AppMeasurement 无法确定是否支持 Java。 图像请求中不存在 `v` 查询字符串。
