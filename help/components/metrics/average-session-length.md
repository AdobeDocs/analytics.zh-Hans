---
title: 平均会话时长（移动设备）
description: 移动设备的平均会话时长。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 29%

---

# 平均会话时长（移动设备）

“平均会话时长（移动设备）”[量度](overview.md)显示给定维度项在每个维度项中存在的平均时间量。 它与[[!UICONTROL 每次访问逗留时间（秒）]](time-spent-per-visit.md)量度相似，只是此量度使用Mobile SDK特定的组件作为其计算的一部分。

## 如何计算此量度

此量度使用[生命周期量度](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`计算。
