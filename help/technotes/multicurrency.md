---
description: 介绍如何定义目标货币代码以使多货币支持正常工作。
title: 多货币支持
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 18%

---

# 多货币支持

Adobe提供了多个级别的货币转换，以便贵组织可以在许多报表中实现所需的货币。 转化发生在三个级别：

## 页面级别

您可以使用[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)变量在每个页面上设置所需的货币。 如果页面上的货币与目标报表包的货币不匹配，Adobe会根据当天的汇率执行到报表包货币的货币换算。 将记录转换后的货币。

## 报表包级别

每个报表包都有&#x200B;**基本货币**。 此货币指示所有货币量度的上下文（如[收入](/help/components/metrics/revenue.md)）。 存储的所有货币数据以报表包的基本货币表示。

