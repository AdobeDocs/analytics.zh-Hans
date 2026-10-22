---
title: JavaScript版本
description: 访客浏览器支持的JavaScript版本。
feature: Dimensions
source-git-commit: a68e13c9232ef8d975fd1256168a0addf677f5ac
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 10%
---
# JavaScript版本

“JavaScript版本”[维度](overview.md)报告访客浏览器支持的JavaScript版本。 它不会报告AppMeasurement库的版本。

>[!IMPORTANT]
>
>此维度只能在 Data Warehouse 中使用。 如果要在其他Analytics解决方案中使用JavaScript版本，请考虑在每次点击时将该值复制到[eVar](evar.md)。

## 使用数据填充此维度

AppMeasurement会自动检测浏览器中的JavaScript功能，并在`j`查询字符串参数中发送版本值。 没有要设置的实施变量。 此检测使用旧版JavaScript版本标签；它不是现代ECMAScript功能支持的综合衡量标准。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（自动收集） |
| **Web SDK / XDM字段** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **查询参数** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **批量数据插入API列** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **字节限制** | 5字节 |
| **持久性** | 点击 |

## 维度项目

Dimension项目包括从访客的浏览器（如`1.5`和`1.6`）收集的JavaScript版本值。
