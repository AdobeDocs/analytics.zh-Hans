---
title: 点击类型
description: 确定点击是前景还是背景点击。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# 点击类型

“点击类型”维度确定将点击发送到Adobe数据收集服务器时移动应用程序是处于前台还是后台。 此维度仅与包含移动应用程序数据的报表包相关。 通过AppMeasurement收集的浏览器数据始终以“前景”的形式报告点击。

## 用数据填充此维

此维度适用于4.13.6或更高版本上的所有移动SDK实施。 如果您不使用移动SDK，则所有点击“前景”维值下的列表。 If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## 维值

维值包括 `"Foreground"` 和 `"Background"`。 未在手机应用程序背景中发送的任何点击都属于 `"Foreground"` 维度值。 移动应用程序在后台发送的任何点击都属于 `"Background"` 维度值。
