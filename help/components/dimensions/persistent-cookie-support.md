---
title: 永久性 Cookie 支持
description: 确定访客是否能够支持永久 Cookie。
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
source-wordcount: '243'
ht-degree: 67%
---
# 永久性 Cookie 支持

“永久性Cookie支持”维度[维度](overview.md)显示点击是否使用了来自永久来源的访客标识符。 最常见的持久源来自 Cookie，但也可以使用移动标头和其他源。

## 使用数据填充此维度

Adobe可根据点击的访客标识符是否源自通常持续存在的来源（例如Cookie）来确定此维度服务器端。 没有要设置的变量，它可开箱即用于所有实施。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生服务器端） |
| **Web SDK / XDM字段** | 无（派生服务器端） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

* **`Enabled`**：点击的访客标识符来自通常持续存在的来源。 最常见的示例包括 `aid`、`fid` 或 `mid` 查询字符串参数，因为它们从 Cookie 派生自己的值。
* **`Disabled`**：点击的访客标识符来自 Adobe 未识别为永久性来源的来源，例如 IP + 用户代理字符串。 此维度项还包括使用 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 变量的自定义访客 ID。

## “Cookie 支持”和“永久性 Cookie 支持”之间的区别

* **Cookie 支持**：AppMeasurement 尝试设置通用 Cookie。 此维度项基于 Cookie 是否设置成功。
* **永久性 Cookie 支持**：此维度项基于点击的标识符是否源自永久性来源，例如 Cookie。
