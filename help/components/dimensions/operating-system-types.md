---
title: 操作系统类型
description: 操作系统，不考虑版本。
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 81%

---

# 操作系统类型

“操作系统类型”维度显示访客使用的整体操作系统，而不考虑特定版本。此维度不仅有助于了解最常用的特定操作系统和版本，而且还有助于了解访客使用的典型操作系统平台。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。如果您使用AppMeasurement库(例如，通过Adobe Experience Platform中的标记)，则此维度可开箱即用。

## 维度项目

维度项目包括所使用的操作系统类型。示例包括 `"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"` 和 `"Apple iOS"`。
