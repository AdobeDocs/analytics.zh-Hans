---
title: 平均会话时长（移动设备）
description: 移动设备的平均会话时长。
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 90%

---

# 平均会话时长（移动设备）

“平均会话时长（移动设备）”量度显示给定维度项目在每个维度项目中存在的平均时间。它与[网站平均逗留时间](average-time-on-site.md)量度相似，只是此量度使用 Mobile SDK 特定组件作为其计算的一部分。

## 如何计算此量度

此量度使用[移动设备量度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'` 计算。
