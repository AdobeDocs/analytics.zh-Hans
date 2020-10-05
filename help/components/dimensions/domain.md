---
title: 域
description: 访客用来访问Internet的组织或ISP。
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 7%

---


# 域

“域”维报告访客用于访问Internet的接入点。

## 使用数据填充此维度

Adobe与 [Digital Element合作](https://www.digitalelement.com/) ，确定接入点域。 包括反向DNS查找在内的几种方法用于确定接入点域。 它不需要任何配置，也没有要填充的变量。 它适用于所有AppMeasurement实施。

## Dimension项

维项目的示 `comcast.net`例包 `rr.com`括、 `sbcglobal.net`、和 `amazonaws.com`。 请注意，这些域是接入点，不一定是代表ISP或组织的域。

Dimension `None` 值表示接入点IP地址的所有者未提供域。
