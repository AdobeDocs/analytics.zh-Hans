---
title: 浏览器类型
description: 制作浏览器的组织。
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 3%

---


# 浏览器类型

“浏览器类型”维列表组织创建访客使用的浏览器。 当您想要了解访客使用的浏览器总体时，此维度很有用。 它提供了“浏览器”维的值，因为它不将同一浏览器的不同版本列表为单独的维值。

## 用数据填充此维

此维引用Adobe内部的查找表。 查找值基于图像请 `User-Agent` 求中的HTTP头。 如果您使用AppMeasurement库（如通过Adobe Experience Platform Launch），此维度将开箱即用。

## 维值

维值包括制作浏览器的组织。 常见维值 `"Google"` 包括(创 [!DNL Chrome]建者 `"Apple"` )、(创 [!DNL Safari]建者)、 `"Microsoft"` (创建者 [!DNL Edge]) `"Mozilla"`[!DNL Firefox]和（创建者）。
