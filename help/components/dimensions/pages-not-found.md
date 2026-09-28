---
title: 页面未找到（维度）
description: 在您的网站上返回错误的 URL。
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: 'https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc'
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 50%
---
# 页面未找到

>[!BEGINSHADEBOX]

*此帮助页介绍“页面未找到”如何作为[维度](overview.md)使用。 有关它如何作为量度使用的信息，请参阅[页面未找到](../metrics/pages-not-found.md)量度页面。*

>[!ENDSHADEBOX]

“页面未找到”维度显示包含错误的 URL。 当您希望减少访客在您的网站上收到的错误数时，此维度很有用。

* 您可以在[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)中使用此维度，以查看访客在点击哪些页面时出现错误。 然后，您可以与组织中的开发团队合作，修复每个页面上的问题链接。
* 您可以将此维度与[反向链接](referrer.md)维度一起使用，以查看访客从外部链接到达您的网站的哪些位置。 然后，您可以实施到所需位置的重定向，或与第三方合作修复链接。

>[!NOTE]
>
>在Data Warehouse中，此维度名为“[!UICONTROL Page Type Error]”。

## 使用数据填充此维度

AppMeasurement 使用 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 变量收集此数据。 当`pageType`设置为`errorPage`时，点击的页面URL将记录为维度项。 如果未定义`pageType`变量或将其设置为任何其他值，则不会收集此维度的数据。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`pageType`](/help/implement/vars/page-vars/pagetype.md) |
| **Web SDK / XDM字段** | [`web.webPageDetails.isErrorPage`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **查询参数** | [`pageType`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<pageType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 不适用 |
| **持久性** | 点击 |

## 维度项目

维度项目包括网站上发生错误的页面的 URL。
