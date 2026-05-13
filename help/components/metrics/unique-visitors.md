---
title: 独特访客
description: 独特访客 ID 的数量。
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
TQID: https://experienceleague.adobe.com/A0NvwoGPFLuS4e857eH-nMgmzAmz0EuGVQVDNBgiN4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 100%

---

# 独特访客

“独特访客”[量度](overview.md)显示访问维度项的访客 ID 的数量。 它是确定流量时最常用的量度之一，因为它提供了对一个维度项常用程度的简要概述。 例如，访客可能在一个月内每天访问您的网站，但仍将其计为一个独特访客。

如果您使用[跨设备分析](../cda/overview.md)，则此指标会被替换为[独特设备](unique-devices.md)指标。

## 每日、每周、每月、每季度和每年独特访客

Analysis Workspace 根据报表的粒度处理独特访客。 例如，如果您使用[天](../dimensions/day.md)维度，您将看到每个维度项目的每日独特访客。 但是，对于报告合计，它会消除自由格式表日期范围的重复独特访客。

## 如何计算此指标

此量度计算某个给定维度项的独特访客 ID 数量。 有关 Adobe Analytics 如何识别独特访客的更多信息，请参阅[访客识别概述](/help/implement/id/overview.md)。
