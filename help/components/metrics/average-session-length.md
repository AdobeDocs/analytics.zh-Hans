---
title: 平均会话时长（移动设备）
description: 移动设备的平均会话长度。
translation-type: tm+mt
source-git-commit: 625af73ad2fbe4b44bce00a122c4e65d8964323f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 9%

---


# 平均会话时长（移动设备）

“平均会话长度（移动）”度量显示给定维值存在于每个维值的平均时间。 它与“平均站点 [停留时间”度量类似](average-time-on-site.md) ，只是此度量使用移动SDK特定组件作为其计算的一部分。

## 如何计算此度量

此度量是使用移动度 [量计算的](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html)`'Total session length' / ('Launches' - 'First launches'`。
