---
description: 已单击的链接名称。
title: Activity Map 链接
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 8%

---

# Activity Map 链接

“Activity Map链接”[维度](overview.md)显示点击次数最多的链接。 您可以使用此维度来比较网站上的哪些链接使用得最多，而不管这些链接是在何处点击的。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`中检索数据。 如果您的实现使用[Activity Map](/help/analyze/activity-map/overview.md)，则此上下文数据变量会在单击链接时自动收集数据。

对于已单击的给定链接，Activity Map将依次搜索以下内容：

1. `s_objectID`变量
1. 链接的内部文本
1. 图像的`alt`属性
1. `title`属性
1. 图像的`src`属性
1. 表单的`action`属性

如果点击的元素不包含上述任何条件，则Activity Map不会收集该点击的数据。

## 维度项

Dimension项目包括访客点击的链接文本或其他链接属性。 您组织的网站结构和实施决定了收集的确切值。
