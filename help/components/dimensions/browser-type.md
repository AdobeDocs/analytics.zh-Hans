---
title: 浏览器类型
description: 开发浏览器的组织。
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
TQID: https://experienceleague.adobe.com/Qb4g-5RXrK42ui4xG86YEv3ozVqmqHrn9Bj5zqXmzPU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
source-wordcount: '186'
ht-degree: 52%
---
# 浏览器类型

“浏览器类型”[维度](overview.md)列出了制作访客所用浏览器的组织。 如果您想要了解访客使用的主要浏览器，此维度非常有用。 相比“浏览器”维度，它更有价值，因为它不会将同一浏览器的不同版本列为单独的维度项。

## 使用数据填充此维度

Adobe从`User-Agent` HTTP标头派生此维度，并将其与Adobe与[DeviceAtlas](https://deviceatlas.com/)合作维护的内部查找表进行匹配。 没有要设置的变量。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自用户代理） |
| **Web SDK / XDM字段** | 无（派生自用户代理） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)时启用[!UICONTROL 设备查找]。

## 维度项目

维度项目包括开发浏览器的组织。 常见的维度项目包括 `"Google"`（[!DNL Chrome] 的创建者）、`"Apple"`（[!DNL Safari] 的创建者）、`"Microsoft"`（[!DNL Edge] 的创建者）以及 `"Mozilla"`（[!DNL Firefox] 的创建者）。
