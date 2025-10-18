---
title: 独特访客
description: 独特访客 ID 的数量。
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: f26f406848ab26092738089aac64ed9b4fc08019
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 83%

---

# 独特访客

“独特访客”[量度](overview.md)显示访问维度项的访客 ID 的数量。它是确定流量时最常用的指标之一，因为它提供了对维度项目常用程度的简要概述。例如，访客可能在一个月内每天访问您的网站，但仍将其计为一个独特访客。

如果您使用[跨设备分析](../cda/overview.md)，则此指标会被替换为[独特设备](unique-devices.md)指标。

## 每日、每周、每月、每季度和每年独特访客

Analysis Workspace 根据报表的粒度处理独特访客。例如，如果您使用[天](../dimensions/day.md)维度，您将看到每个维度项目的每日独特访客。但是，对于报表合计，它会消除自由形式表日期范围的重复独特访客。

## 如何计算此指标

此量度计算给定维度项目的独特访客ID数量。 有关Adobe Analytics如何识别独特访客的更多信息，请参阅[访客识别概述](/help/implement/id/overview.md)。
