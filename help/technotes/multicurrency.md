---
description: 介绍如何定义目标货币代码以使多货币支持正常工作。
title: 多货币支持
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# 多货币支持

Adobe提供了多个级别的货币转换，以便贵组织在许多报表中均可获得所需的货币。 转化发生在三个级别：

## 页面级别

您可以使用 [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 变量来设置每个页面上的所需货币。 如果页面上的货币与目标报表包的货币不匹配，则Adobe会根据当天的汇率将货币折换为报表包的货币。 将记录转换后的货币。

## 报表包级别

每个报表包都有一个 **基础货币**. 此货币指示所有货币量度的上下文(例如 [收入](/help/components/metrics/revenue.md))。 存储的所有货币数据以报表包的基本货币表示。

## 用户级别

对于Reports &amp; Analytics，用户可以在下方设置与报表包基本货币不同的货币 [报表设置](/help/analyze/reports-analytics/report-settings.md). 此设置是非破坏性的，这意味着它不会更改基础数据。 相反，它将基本货币兑换应用于根据今天的汇率查看的所有报告。 如果您在不同日期查看同一报表，则数字可能会因不同的每日汇率而更改。

Analysis Workspace目前不提供用户级别的货币换算。
