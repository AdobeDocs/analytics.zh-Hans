---
title: 永久 Cookie 支持
description: 确定访客是否能够支持永久 Cookie。
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 11%

---

# 永久 Cookie 支持

“永久Cookie支持”维度显示点击是否使用源自永久源的访客标识符。 最常见的永久性源来自Cookie，但也可以使用移动头和其他源。

## 使用数据填充此维度

Adobe根据点击的标识符来源确定此维度在服务器端的值。 无法直接设置。 它可开箱即用于所有实施。

## 维度项目

* **`Enabled`**:点击的访客标识符来自通常持续存在的源。最常见的示例包括`aid`、`fid`或`mid`查询字符串参数，因为它们的值来自Cookie。
* **`Disabled`**:点击的访客标识符来自Adobe无法识别为永久性的源，如IP +用户代理字符串。此维度项目还包含使用[`visitorID`](/help/implement/vars/config-vars/visitorid.md)变量的自定义访客ID。

## “Cookie支持”与“永久Cookie支持”的区别

* **Cookie支持**:AppMeasurement尝试设置通用Cookie。维度项目基于Cookie是否成功设置。
* **永久Cookie支持**:维度项目基于点击的标识符是否源自永久性源（如Cookie）。
