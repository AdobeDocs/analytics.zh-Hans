---
title: 页面 URL
description: 页面的 URL。
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 52%
---
# 页面 URL

“页面URL”[维度](overview.md)列出了您网站上的URL。

>[!IMPORTANT]
>
>此维度只能在 Data Warehouse 中使用。 如果您要在其他 Analytics 解决方案中使用 URL 维度，请考虑在每次点击时将该值复制到 [eVar](evar.md) 中。

## 使用数据填充此维度

AppMeasurement在每个[页面查看调用(`t()`)](/help/implement/vars/functions/t-method.md)时自动收集页面URL。 您可以使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 变量覆盖收集的值。 如果URL的长度大于255字节，则溢出将存储在`-g`查询字符串参数中。 URL中包含协议和查询字符串。 [链接跟踪调用(`tl()`)](/help/implement/vars/functions/tl-method.md)始终剥离此维度，即使URL值存在也是如此。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`pageURL`](/help/implement/vars/page-vars/pageurl.md) |
| **Web SDK / XDM字段** | [`web.webPageDetails.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **查询参数** | [`g`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<pageUrl>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 255字节（没有带溢出的固定限制） |
| **持久性** | 点击 |

## 使用 URL 填充 eVar

Adobe 建议将 eVar 设置为串联字符串 `window.location.hostname + window.location.pathname`。 此字符串的效果通常比 `window.location.href` 更好，因为它忽略了协议、查询字符串和锚点标签。

如果您希望 eVar 与 Data Warehouse 中的“页面 URL”维度完全匹配，则可以使用[动态变量](/help/implement/vars/page-vars/dynamic-variables.md)并在每次点击时将 eVar 设置为 `D=g`。

## 维度项目

维度项目包括网站上页面的 URL。
