---
title: Cookie 支持
description: 确定浏览器是否支持 Cookie。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 38%
---
# Cookie 支持

“Cookie支持”维度[维度](overview.md)报告浏览器是否支持给定点击的Cookie。 此维度对于确定使用支持 Cookie 的浏览器和有意禁用 Cookie 的访客比例非常有用。

## 使用数据填充此维度

Cookie支持是自动收集的，客户端：AppMeasurement尝试设置名为`s_cc`的Cookie，然后报告它是否存在 — `Y`（如果浏览器支持并启用了Cookie）或`N`（如果禁用Cookie）。 它可以在任何AppMeasurement或Web SDK（标记）实施中开箱即用 — 没有要设置的变量。 如果您在AppMeasurement或Web SDK之外收集数据（例如通过API），请在每次点击时发送`Y`或`N`。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（自动收集） |
| **Web SDK / XDM字段** | 无（自动收集） |
| **查询参数** | [`k`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<cookiesEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 1字节 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括 `Enabled`、`Disabled` 和 `Unknown`。

* **`Enabled`**：浏览器支持 Cookie 并已将其启用。
* **`Disabled`**：浏览器不支持 Cookie，或者访客禁用了 Cookie。
* **`Unknown`**：AppMeasurement 无法确定 Cookie 支持。 图像请求中不存在 `k` 查询字符串。
