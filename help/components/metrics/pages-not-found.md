---
title: 页面未找到
description: 包含错误的点击数。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---

# 页面未找到

*此帮助页介绍了“页面未找到”如何作为维度使用。有关更多信息，请参阅[页面未找到](../dimensions/pages-not-found.md)维度。*

“页面未找到”量度显示页面包含错误的点击次数。当您想要查看哪些页面或 URL 包含错误消息（例如 404）时，此量度很有价值，便于您确定错误的原因并进行修复。

## 如何计算此量度

此量度计算 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 变量等于 `"errorPage"` 值的所有点击数。它是[页面未找到](../dimensions/pages-not-found.md)维度的等效量度。
