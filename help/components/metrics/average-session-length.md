---
title: 平均会话时长（移动设备）
description: 移动设备的平均会话时长。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 47d5a532505aff48d43972836c78620870bd8221
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 65%

---

# 平均会话时长（移动设备）

“平均会话时长（移动设备）”量度显示给定维度项目在每个维度项目中存在的平均时间。它类似于 [每次访问逗留时间[秒]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) 量度，但此量度使用Mobile SDK特定组件作为其计算的一部分。

## 如何计算此量度

此量度使用[移动设备量度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hans) `'Total session length' / ('Launches' - 'First launches'` 计算。
