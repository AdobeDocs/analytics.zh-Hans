---
title: Activity Map 页面
description: 单击链接时的页面名称。
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 6%

---

# Activity Map 页面

“Activity Map页面”[维度](overview.md)显示访客在点击链接时所在的页面。 您可以使用此维度来确定哪些页面包含的链接被点击的次数最多。 Activity Map叠加图也使用此维度来确定要显示的链接。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`中检索数据。 如果您的实施使用[Activity Map](/help/analyze/activity-map/overview.md)，则此上下文数据变量会在单击链接时自动收集数据。

对于已单击的给定链接，此上下文数据变量将收集[页面](page.md)维度中的值。 如果页面维度不包含值，则改用[页面URL](page-url.md)维度（与页面维度使用的回退类似）。 Activity Map数据通常会在点击链接后的下一次点击中发送。 利用此维度，可确定点击链接时的页面值，而不是发送数据时的页面值。

## 维度项目

Dimension项目包括[页面](page.md)维度中找到的所有值。
