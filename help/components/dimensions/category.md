---
title: 类别
description: 点击的产品类别。
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: 'https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 63%
---
# 类别

“类别”[维度](overview.md)报告点击的产品类别。 此维度对于使用 `products` 变量且想要查看产品类别相关的量度（例如，最畅销的产品或查看次数最多的产品）的实施非常有用。 如果您的网站上没有任何产品，则此维度可能会特意留空。

## 使用数据填充此维度

此维度引用[`products`](/help/implement/vars/page-vars/products.md)变量中的产品类别，它是第一个分号(`;`)之前的所有内容。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Web SDK / XDM字段** | [`productListItems[].productCategories[].categoryID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **查询参数** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 Adobe 建议您使用“产品”和“类别”维度将各个产品分组为有意义的类别。

>[!TIP]
>
>在 Adobe Analytics 的先前版本中，“类别”维度由于其处理架构而存在一些限制。 现已移除这些限制，允许您使用任何量度和任何细分。
