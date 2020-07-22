---
title: 点击类型
description: 确定点击是前景还是背景点击。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# 点击类型

“点击类型”维度确定将点击发送到Adobe数据收集服务器时移动应用程序是处于前台还是后台。 此维度仅与包含移动应用程序数据的报表包相关。 通过AppMeasurement收集的浏览器数据始终以“前景”的形式报告点击。

## 用数据填充此维

此维度适用于4.13.6或更高版本上的所有移动SDK实施。 如果您不使用移动SDK，则“前景”维项下的所有点击列表。 If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## 维项

维项包括 `"Foreground"` 和 `"Background"`。 未在手机应用程序背景中发送的任何点击都属于维 `"Foreground"` 度项。 移动应用程序在后台发送的任何点击都属于维 `"Background"` 度项。
