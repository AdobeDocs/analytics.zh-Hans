---
title: 页面
description: 页面名称。
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: 'https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 54%
---
# 页面

“页面”[维度](overview.md)列出了您网站上的页面名称。 它是 Adobe Analytics 中最常用的维度之一，因为它可让您洞察网站上的哪些页面效果最佳。

此维度与[网站区域](site-section.md)维度和[服务器](server.md)维度相关。 页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

在[页面查看调用(`t()`)](/help/implement/vars/functions/t-method.md)中设置[`pageName`](/help/implement/vars/page-vars/pagename.md)变量。 如果未设置`pageName`变量，则此维度将回退为使用[`pageURL`](/help/implement/vars/page-vars/pageurl.md)变量。 [链接跟踪调用(`tl()`)](/help/implement/vars/functions/tl-method.md)始终剥离此维度，即使存在`pageName`值也是如此。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`pageName`](/help/implement/vars/page-vars/pagename.md) |
| **Web SDK / XDM字段** | [`web.webPageDetails.name`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **查询参数** | [`pageName`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<pageName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

## 维度项目

维度项目包括您的网站上的页面名称。 您的组织会确定您要使用的特定维度项目。 有些组织直接使用 `document.title`，而另一些组织则制定自定义痕迹导航。 无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。

>[!NOTE]
>
>Analysis Workspace 默认使用最后接触归因，并且可以选择使用任何归因模型。
