---
title: 页面
description: 页面名称。
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 80%

---

# 页面

“页面”[维度](overview.md)列出了您网站上的页面名称。 它是 Adobe Analytics 中最常用的维度之一，因为它可让您洞察网站上的哪些页面效果最佳。

此维度与[网站区域](site-section.md)维度和[服务器](server.md)维度相关。 页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从[页面查看调用 (`t()`)](/help/implement/vars/functions/t-method.md) 中的 [`pageName` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。 [链接跟踪调用 (`tl()`)](/help/implement/vars/functions/tl-method.md) 始终剥离此维度，即使存在 `pageName` 查询字符串也是如此。

AppMeasurement 使用 [`pageName`](/help/implement/vars/page-vars/pagename.md) 变量收集此数据。 如果未设置`pageName`变量，则此维度将回退为使用[`pageURL`](/help/implement/vars/page-vars/pageurl.md)变量。

## 维度项目

维度项目包括您的网站上的页面名称。 您的组织会确定您要使用的特定维度项目。 有些组织直接使用 `document.title`，而另一些组织则制定自定义痕迹导航。 无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。

>[!NOTE]
>
>Analysis Workspace 默认使用上一个归因，并且可以选择使用任何归因模型。
