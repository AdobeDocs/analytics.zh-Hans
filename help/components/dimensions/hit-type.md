---
title: 点击类型
description: 确定点击是前台还是后台点击。
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 84%

---

# 点击类型

“点击类型” [维度](overview.md) 确定将点击发送到Adobe数据收集服务器时，移动设备应用程序是处于前台还是后台。 此维度仅与包含移动设备应用程序数据的报表包相关。通过 AppMeasurement 收集的浏览器数据始终将点击报告为“前台”。

## 使用数据填充此维度

此维度可开箱即用于版本 4.13.6 或更高版本上的所有 Mobile SDK 实施。如果您不使用 Mobile SDK，则所有点击均列在“前台”维度项目下。如果选中“禁用计算后台点击量的旧版报告和归因”，则后台点击量将仅显示在[虚拟报表包](../vrs/vrs-mobile-visit-processing.md)中。

## 维度项目

维度项目包括 `"Foreground"` 和 `"Background"`。不是在移动设备应用程序后台发送的任何点击属于 `"Foreground"` 维度项目。在移动设备应用程序处于后台时发送的任何点击属于 `"Background"` 维度项目。
