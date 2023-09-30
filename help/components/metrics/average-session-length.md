---
title: 平均会话时长（移动设备）
description: 移动设备的平均会话时长。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 26%

---

# 平均会话时长（移动设备）

“平均会话时长（移动设备）” [量度](overview.md) 显示给定维度项在每个维度项中存在的平均时间。 它类似于 [[!UICONTROL 每次访问逗留时间（秒）]](time-spent-per-visit.md) 量度，只不过此量度使用Mobile SDK特定的组件作为其计算的一部分。

## 如何计算此指标

此指标的计算方式为 [生命周期量度](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
