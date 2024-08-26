---
title: 按区域划分的 Activity Map 链接
description: 链接和区域的拼接值。
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# 按区域划分的 Activity Map 链接

“按地区Activity Map链接”[维度](overview.md)显示[Activity Map链接](activity-map-link.md)和[Activity Map地区](activity-map-link-by-region.md)的串联。 当您具有名称相似但位于网站不同区域的链接时，此维度很有用。 例如，如果您有多个指向主页的链接，这些链接全部标记为“主页”，则可以使用此维度区分每个网站区域中的这些链接。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`和`c.a.activitymap.region`中检索数据。 这两个值通过管道(`|`)连接和分隔。 如果您的实现使用[Activity Map](/help/analyze/activity-map/overview.md)，则这些上下文数据变量会在单击链接时自动收集数据。

## 维度项

Dimension项包含来自[Activity Map链接](activity-map-link.md)和[Activity Map地区](activity-map-link-by-region.md)的值。 您组织的网站结构和实施决定了收集的确切值。
