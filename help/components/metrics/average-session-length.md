---
title: 平均会话时长（移动设备）
description: 移动设备的平均会话时长。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 41%

---

# 平均会话时长（移动设备）

“平均会话时长（移动设备）” [量度](overview.md) 显示给定维度项在每个维度项中存在的平均时间。 它类似于 [每次访问逗留时间[秒]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) 量度，只不过此量度使用Mobile SDK特定组件作为其计算的一部分。

## 如何计算此量度

此量度使用[移动设备量度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans) `'Total session length' / ('Launches' - 'First launches'` 计算。
