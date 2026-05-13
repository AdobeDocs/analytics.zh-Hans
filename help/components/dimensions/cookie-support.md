---
title: Cookie 支持
description: 确定浏览器是否支持 Cookie。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 92%

---

# Cookie 支持

“Cookie支持”维度[维度](overview.md)报告浏览器是否支持给定点击的Cookie。 此维度对于确定使用支持 Cookie 的浏览器和有意禁用 Cookie 的访客比例非常有用。

## 使用数据填充此维度

此维度从图像请求中的[`k`查询字符串](/help/implement/validate/query-parameters.md)收集数据。 AppMeasurement 尝试设置名为 `s_cc` 的 Cookie，然后检测该 Cookie 是否存在。 结果会生成查询字符串参数值 `Y`（如果浏览器支持并启用了 Cookie）或 `N`（如果浏览器禁用了 Cookie）。 如果您使用 AppMeasurement（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。 如果您使用 AppMeasurement 以外的数据收集方法（例如通过 API），请确保在每次点击时包含 `k` 查询字符串参数，并具有值 `Y` 或 `N`。

## 维度项目

维度项目包括 `Enabled`、`Disabled` 和 `Unknown`。

* **`Enabled`**：浏览器支持 Cookie 并已将其启用。
* **`Disabled`**：浏览器不支持 Cookie，或者访客禁用了 Cookie。
* **`Unknown`**：AppMeasurement 无法确定 Cookie 支持。 图像请求中不存在 `k` 查询字符串。
