---
title: 按区域划分的 Activity Map 链接
description: 链接和区域的拼接值。
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
TQID: 'https://experienceleague.adobe.com/xvYVA064hA0rsBdnLpxXllq3PD0zYAikFRjc6xNErvg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%
---
# 按区域划分的 Activity Map 链接

“按地区划分的Activity Map链接”维度[维度](overview.md)显示[Activity Map链接](activity-map-link.md)和[Activity Map地区](activity-map-link-by-region.md)的串联。 当您具有名称相似但位于网站不同区域的链接时，此维度很有用。 例如，如果您有多个指向主页的链接，这些链接全部标记为“主页”，则可以使用此维度区分每个网站区域中的这些链接。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`和`c.a.activitymap.region`中检索数据。 这两个值通过管道(`|`)连接和分隔。 如果您的实施使用[Activity Map](/help/analyze/activity-map/overview.md)，则这些上下文数据变量会在单击链接时自动收集数据。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（由[Activity Map](/help/analyze/activity-map/overview.md)模块收集） |
| **Web SDK / XDM字段** | 无（由[Activity Map](/help/analyze/activity-map/overview.md)模块收集） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 255字节 |
| **持久性** | 不适用 |

## 维度项目

Dimension项目包含来自[Activity Map链接](activity-map-link.md)和[Activity Map地区](activity-map-link-by-region.md)的值。 您组织的网站结构和实施决定了收集的确切值。
