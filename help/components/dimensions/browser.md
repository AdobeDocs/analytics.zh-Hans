---
title: 浏览器
description: 使用的浏览器的名称和版本。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# 浏览器

“浏览器”维度报告发送点击的浏览器的名称和版本。 此维度有助于了解访客使用的最常见浏览器。 测试新版网站时，您可以在此维度的顶级浏览器上运行这些测试，以最大限度地提高质量控制工作。

## 用数据填充此维

此维引用Adobe内部的查找表。 查找值基于图像请 `User-Agent` 求中的HTTP头。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，则此维度开箱即用。

## 维项

维项目包括使用的浏览器名称和版本。 同一浏览器的不同版本是不同的维度项目。

某些维项目包含 `"(unknown version)"` 的不是版本号。 此维度项引用了Adobe尚未添加到其查找表中的最新浏览器版本。 由于浏览器经常更新， `"(unknown version)"` 因此给定浏览器是常用的和临时的。 Adobe通常在每月维护版本期间更新查找表。
