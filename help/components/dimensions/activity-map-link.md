---
description: 已单击的链接名称。
title: Activity Map 链接
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
TQID: 'https://experienceleague.adobe.com/A5HaPb0TghRKVykJ9V2UMJ0mlsYElLkCyBwxzTd6VII'
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
source-wordcount: '196'
ht-degree: 11%
---
# Activity Map 链接

“Activity Map链接”[维度](overview.md)显示点击次数最多的链接。 您可以使用此维度来比较网站上的哪些链接使用得最多，而不管这些链接是在何处点击的。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`中检索数据。 如果您的实施使用[Activity Map](/help/analyze/activity-map/overview.md)，则此上下文数据变量会在单击链接时自动收集数据。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（由[Activity Map](/help/analyze/activity-map/overview.md)模块收集） |
| **Web SDK / XDM字段** | 无（由[Activity Map](/help/analyze/activity-map/overview.md)模块收集） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 255字节 |
| **持久性** | 不适用 |

对于已单击的给定链接，Activity Map会搜索以下内容（按顺序）：

1. `s_objectID`变量
1. 链接的内部文本
1. 图像的`alt`属性
1. `title`属性
1. 图像的`src`属性
1. 表单的`action`属性

如果点击的元素不包含上述任何条件，Activity Map将不会收集该点击的数据。

## 维度项目

Dimension项目包括访客点击的链接文本或其他链接属性。 您组织的网站结构和实施决定了收集的确切值。
