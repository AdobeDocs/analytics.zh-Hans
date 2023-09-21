---
title: 未找到页面（指标）
description: 包含错误的点击数。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 48%

---

# 页面未找到

*此帮助页介绍了“页面未找到”如何作为维度使用。有关更多信息，请参阅[页面未找到](../dimensions/pages-not-found.md)维度。*

“页面未找到” [量度](overview.md) 显示访客遇到错误时设置或保留维度的点击次数。 当您想要查看哪些页面或URL包含错误消息（例如404）时，此量度很有价值。 然后，您可以将此信息传递给Web开发团队，他们可确定错误的原因并进行修复。

## 如何计算此量度

此量度计算 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 变量等于 `"errorPage"` 值的所有点击数。它是[页面未找到](../dimensions/pages-not-found.md)维度的等效量度。
