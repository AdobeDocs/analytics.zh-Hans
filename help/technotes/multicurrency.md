---
description: 介绍如何定义目标货币代码以使多货币支持正常工作。
title: 多货币支持
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 16%

---

# 多货币支持

Adobe提供了多个货币转换级别，以便贵组织在许多报表中均可获得所需的货币。 转化发生在三个级别：

## 页面级别

您可以使用[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)变量在每个页面上设置所需的货币。 如果页面上的货币与目标报表包的货币不匹配，Adobe会根据当天的汇率执行到报表包所用货币的货币换算。 将记录转换后的货币。

## 报表包级别

每个报表包都有&#x200B;**基本货币**。 此货币指示所有货币量度的上下文（如[收入](/help/components/metrics/revenue.md)）。 存储的所有货币数据以报表包的基本货币表示。

