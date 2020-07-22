---
title: 已启用 Java
description: 确定是否在浏览器中启用Java。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 1%

---


# 已启用 Java

“启用Java”维度确定当时浏览器是否启用了Java。 如果您希望在您的站点上引入基于Java的功能，并想了解有多少访客已经启用了Java，则此功能非常有用。 对于已禁用Java的用户，您可以提供如何启用Java的替代或说明。

## 用数据填充此维

此维从图像请求中的 [`v` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement通过检测浏览器中是否启用Java来收集此数据。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，则此维度开箱即用。 如果您在AppMeasurement外使用查询收集方法（如通过API），请确保包含包含“Y”或“N”的字符串参数（如果您希望使用此维）。 `v`

## 维项

维项包括“已启用”、“已禁用”和“未知”。

* **已启用**: 浏览器中启用了Java。 查询 `v` 字符串包含值“Y”。
* **禁用**: Java在浏览器中被禁用，或者不支持Java。 查询 `v` 字符串包含值“N”。
* **未知**: AppMeasurement无法确定Java支持。 图 `v` 像请求中不存在查询字符串。
