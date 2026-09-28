---
title: 语言
description: 浏览器中的首选语言设置。
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: 'https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs'
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 65%
---
# 语言

“语言”[维度](overview.md)显示访客喜欢在其中查看内容的最常用语言。 当您想要了解访客最常使用的语言以帮助进行本地化时，此维度很有用。

>[!NOTE]
>
>此维度不会收集网站的语言。 如果要在某个维度中收集网站的语言，Adobe 建议使用自定义变量，例如 [eVar](evar.md)。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。 查找值基于图像请求中的 `Accept-Language` HTTP 标头。 它可以在任何AppMeasurement或Web SDK（标记）实施中开箱即用 — 没有要设置的变量。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（HTTP标头） |
| **Web SDK / XDM字段** | 无（HTTP标头） |
| **查询参数** | 无（使用`Accept-Language`标头） |
| **XML标记** | [`<language>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括访客首选语言的友好名称。 示例包括 `"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"` 和 `"Spanish (Spain)"`。 如果图像请求在 HTTP 标头中不包含有效语言，则维度项目为 `"None"`。
