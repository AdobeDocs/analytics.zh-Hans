---
title: 操作系统
description: 访客的操作系统。
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# 操作系统

“操作系统”维度显示访客使用的操作系统和版本。如果您的 Web 资产上具有特定于操作系统的功能，则此维度可以帮助您了解最常用的操作系统。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。如果您使用AppMeasurement库(例如，通过Adobe Experience Platform中的标记)，则此维度可开箱即用。

## 维度项目

维度项目包括访客使用的操作系统。示例包括 `"Windows 10"`、`"OS X 10.15"` 和 `"Android 9"`。
