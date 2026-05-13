---
title: 页面未找到（维度）
description: 在您的网站上返回错误的 URL。
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 78%

---

# 页面未找到

*此帮助页介绍“页面未找到”如何作为[维度](overview.md)使用。 有关它如何作为量度使用的信息，请参阅[页面未找到](../metrics/pages-not-found.md)量度页面。*

“页面未找到”维度显示包含错误的 URL。 当您希望减少访客在您的网站上收到的错误数时，此维度很有用。

* 您可以在[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)中使用此维度，以查看访客在点击哪些页面时出现错误。 然后，您可以与组织中的开发团队合作，修复每个页面上的问题链接。
* 您可以将此维度与[反向链接](referrer.md)维度一起使用，以查看访客从外部链接到达您的网站的哪些位置。 然后，您可以实施重定向到所需的位置，或与第三方合作修复链接。

## 使用数据填充此维度

此维度从图像请求中的 [`pageType` 和 `g` 查询字符串](/help/implement/validate/query-parameters.md) 中检索数据。 如果 `pageType` 查询字符串等于 `errorPage`，则会记录 `g` 查询字符串（页面 URL）。 AppMeasurement 使用 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 变量收集此数据。 如果未定义 `pageType` 变量或将其设置为 `errorPage` 之外的任何其他变量，则不会收集此维度的数据。

## 维度项目

维度项目包括网站上发生错误的页面的 URL。
