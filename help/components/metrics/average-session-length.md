---
title: 平均会话时长（移动设备）
description: 移动设备的平均会话时长。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
TQID: https://experienceleague.adobe.com/4TaQP7sH0pADpnwoQR-aqOpKqKvcuUXU1vmE3-ETOzM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 83
ht-degree: 36%

---

# 平均会话时长（移动设备）

“平均会话时长（移动设备）”[量度](overview.md)显示给定维度项在每个维度项中存在的平均时间量。 它类似于[[!UICONTROL 每次访问逗留时间（秒）]](time-spent-per-visit.md)指标，只是此指标使用特定于SDK的移动设备组件作为其计算的一部分。

## 如何计算此指标

此量度使用[生命周期量度](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`计算。
