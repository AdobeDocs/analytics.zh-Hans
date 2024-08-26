---
title: Activity Map 页面
description: 单击链接时的页面名称。
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Activity Map 页面

“Activity Map页面”[维度](overview.md)显示访客在点击链接时所在的页面。 您可以使用此维度来确定哪些页面包含的链接被点击的次数最多。 Activity Map叠加图也使用此维度来确定要显示的链接。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`中检索数据。 如果您的实现使用[Activity Map](/help/analyze/activity-map/overview.md)，则此上下文数据变量会在单击链接时自动收集数据。

对于已单击的给定链接，此上下文数据变量将收集[页面](page.md)维度中的值。 如果页面维度不包含值，则改用[页面URL](page-url.md)维度（与页面维度使用的回退类似）。 Activity Map数据通常会在点击链接后的下一次点击中发送。 利用此维度，可确定点击链接时的页面值，而不是发送数据时的页面值。

## 维度项

Dimension项包含在[页面](page.md)维度中找到的所有值。
