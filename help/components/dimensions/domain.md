---
title: 域
description: 访客用来访问 Internet 的组织或 ISP。
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 89%

---

# 域

“域” [维度](overview.md) 报告访客用于访问Internet的访问点。

## 使用数据填充此维度

Adobe 合作伙伴使用 [Digital Element](https://www.digitalelement.com/) 确定访问点域。有包括 DNS 反向查询在内的多种方法可用于确定访问点域。它无需任何配置，也没有要填充的变量。它可开箱即用于所有 AppMeasurement 实施。

## 维度项目

维度项目示例包括 `comcast.net`、`rr.com`、`sbcglobal.net` 和 `amazonaws.com`。请注意，这些域是访问点，并不一定是表示 ISP 或组织的域。

维度值 `None` 意味着访问点 IP 地址的所有者没有提供域。
