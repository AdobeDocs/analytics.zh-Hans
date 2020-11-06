---
title: 域
description: 访客用来访问 Internet 的组织或 ISP。
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 41%

---


# 域

“域”维报告访客用于访问Internet的接入点。

## 使用数据填充此维度

Adobe与 [Digital Element合作](https://www.digitalelement.com/) ，确定接入点域。 包括反向DNS查找在内的几种方法用于确定接入点域。 它无需任何配置，也没有要填充的变量。它可开箱即用于所有 AppMeasurement 实施。

## 维度项目

维度项目示例包括 `comcast.net`、`rr.com`、`sbcglobal.net` 和 `amazonaws.com`。请注意，这些域是接入点，不一定是代表ISP或组织的域。

Dimension `None` 值表示接入点IP地址的所有者未提供域。
