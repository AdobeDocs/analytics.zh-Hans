---
title: Cookie 支持
description: 确定浏览器是否支持 Cookie。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 92%

---

# Cookie 支持

“Cookie支持”维度[维度](overview.md)报告浏览器是否支持给定点击的Cookie。 此维度对于确定使用支持 Cookie 的浏览器和有意禁用 Cookie 的访客比例非常有用。

## 使用数据填充此维度

此维度从图像请求中的[`k`查询字符串](/help/implement/validate/query-parameters.md)收集数据。AppMeasurement 尝试设置名为 `s_cc` 的 Cookie，然后检测该 Cookie 是否存在。结果会生成查询字符串参数值 `Y`（如果浏览器支持并启用了 Cookie）或 `N`（如果浏览器禁用了 Cookie）。如果您使用 AppMeasurement（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。如果您使用 AppMeasurement 以外的数据收集方法（例如通过 API），请确保在每次点击时包含 `k` 查询字符串参数，并具有值 `Y` 或 `N`。

## 维度项目

维度项目包括 `Enabled`、`Disabled` 和 `Unknown`。

* **`Enabled`**：浏览器支持 Cookie 并已将其启用。
* **`Disabled`**：浏览器不支持 Cookie，或者访客禁用了 Cookie。
* **`Unknown`**：AppMeasurement 无法确定 Cookie 支持。图像请求中不存在 `k` 查询字符串。
