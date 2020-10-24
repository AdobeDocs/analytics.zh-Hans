---
title: 已启用 Java
description: 确定浏览器中是否已启用 Java。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '216'
ht-degree: 100%

---


# 已启用 Java

“已启用 Java”维度确定当时浏览器是否已启用 Java。如果您要在网站上引入基于 Java 的功能，并且想知道有多少访客已经启用 Java，则此功能非常有用。对于已禁用 Java 的访客，您可以提供替代方案或关于如何启用 Java 的操作说明。

## 使用数据填充此维度

此维度从图像请求中的 [`v` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 通过检测浏览器中是否已启用 Java 来收集此数据。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform Launch），则此维度可开箱即用。如果您使用 AppMeasurement 之外的数据收集方法（例如，通过 API），请确保包括 `v` 查询字符串参数，其中包含“Y”或“N”值（如果您希望使用此维度的话）。

## 维度项目

维度项目包括“已启用”、“已禁用”和“未知”。

* **已启用**：浏览器中已启用 Java。`v` 查询字符串包含“Y”值。
* **已禁用**：浏览器中已禁用 Java，或者不支持 Java。`v` 查询字符串包含“N”值。
* **未知**：AppMeasurement 无法确定是否支持 Java。图像请求中不存在 `v` 查询字符串。
