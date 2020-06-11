---
title: Cookie支持
description: 确定浏览器是否支持Cookie。
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---


# Cookie 支持

“Cookie支持”维度报告浏览器是否支持给定点击的Cookie。 确定使用支持Cookie的浏览器的访客和有意禁用它们的浏览器的比例很有用。

## 用数据填充此维

此维从图像请求中的 [`k` 查询字符串](/help/implement/validate/query-parameters.md) 收集数据。 AppMeasurement尝试设置名为的cookie, `s_cc`然后检测该cookie是否存在。 结果是查询字符串参数值( `Y` 如果浏览器支持并启用了cookie)或 `N` （如果浏览器禁用了cookie）。 如果您使用AppMeasurement（例如通过Adobe Experience Platform Launch），此维度将开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在每次点击时都包含字符串参数，并包含值 `k` 或 `Y``N`。

## 维值

维值 `Enabled`包括 `Disabled`、和 `Unknown`。

* **`Enabled`**: 浏览器支持cookie，并启用它们。
* **`Disabled`**: 浏览器不支持cookie，或访客禁用了它们。
* **`Unknown`**: AppMeasurement无法确定对cookie的支持。 图 `k` 像请求中不存在查询字符串。
