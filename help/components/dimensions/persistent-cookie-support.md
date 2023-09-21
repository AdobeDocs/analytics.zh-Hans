---
title: 永久 Cookie 支持
description: 确定访客是否能够支持永久 Cookie。
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 90%

---

# 永久 Cookie 支持

“永久性Cookie支持” [维度](overview.md) 显示点击是否使用了来自永久来源的访客标识符。 最常见的永久性来源来自 Cookie，但也可以使用移动标头和其他来源。

## 使用数据填充此维度

Adobe 根据点击标识符的来源确定此维度服务器端的值。无法直接设置此值。它可开箱即用于所有实施。

## 维度项

* **`Enabled`**：点击的访客标识符来自通常持续存在的来源。最常见的示例包括 `aid`、`fid` 或 `mid` 查询字符串参数，因为它们从 Cookie 派生自己的值。
* **`Disabled`**：点击的访客标识符来自 Adobe 未识别为永久性来源的来源，例如 IP + 用户代理字符串。此维度项还包括使用 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 变量的自定义访客 ID。

## “Cookie 支持”和“永久性 Cookie 支持”之间的区别

* **Cookie 支持**：AppMeasurement 尝试设置通用 Cookie。此维度项基于 Cookie 是否设置成功。
* **永久性 Cookie 支持**：此维度项基于点击的标识符是否源自永久性来源，例如 Cookie。
