---
title: 自定义事件
description: 存在自定义事件的点击数。
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 19%

---


# 自定义事件

*此帮助页介绍自定义事件如何作为度量。 有关自定义事件如何作为实施变量工作的信息，请参[阅实施用](/help/implement/vars/page-vars/events/events-overview.md)户指南中的事件概述。*

自定义事件度量显示在图像请求中设置给定自定义事件的点击次数。 这些指标对许多实施至关重要，因为它们提供了对每个组织特定事件的洞察。

## 如何计算此度量

根据自定义事件的类型，自定义的计算方式各不相同。 您可以在“报告包”设置中的“成 [功事件](../../admin/admin/c-success-events/success-event.md) ”下检查事件类型。

* **计数器事件**: 默认事件设置。 大多数事件是反事件。 计算匹配自定义事件-存 `event1` 在 `event1000` 于变量的点 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 击数。
* **数字事件**: 对变量中分配给事件的数值进 `events` 行求和。
* **货币事件**: 将货币兑换与当日的汇率进行对比，然后计算变量中每次点击的数值 `events` 值。

可用事件的数量取决于贵组织的 Analytics 合同。大多数使用非传统合同的组织具有 1000 个可用的自定义事件。如果您不确定有多少自定义事件可供使用，请与贵组织的客户经理联系。

Adobe强烈建议您记录在组织的解决方案设计事件中使用每 [个文档的方式](/help/implement/prepare/solution-design.md)。
