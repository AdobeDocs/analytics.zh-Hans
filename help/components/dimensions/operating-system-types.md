---
title: 操作系统类型
description: 不管版本如何，操作系统。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# 操作系统类型

“操作系统类型”维度显示所使用访客的总体操作系统，而不管特定版本。 此维度不仅有助于了解哪些特定操作系统和版本最为常见，而且有助于了解访客使用哪些典型操作系统平台。

## 用数据填充此维

此维引用Adobe内部的查找表。 查找值基于图像请 `User-Agent` 求中的HTTP头。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，则此维度开箱即用。

## 维项

维项包括所使用的操作系统类型。 Examples include `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, and `"Apple iOS"`.
