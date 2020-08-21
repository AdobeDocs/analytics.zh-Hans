---
title: 自定义事件
description: 存在自定义事件的点击数。
translation-type: ht
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---


# 自定义事件

*此帮助页介绍了自定义事件如何充当量度。有关自定义事件如何用为实施变量的信息，请参阅实施用户指南中的[事件概述](/help/implement/vars/page-vars/events/events-overview.md)。*

自定义事件量度会显示在图像请求中设置给定自定义事件的点击次数。这些量度对许多实施而言非常重要，因为它们会提供针对每个组织特定事件的洞察信息。

## 如何计算此量度

自定义事件的计算方式各不相同，具体取决于其所属类型。您可以在报表包设置中的[成功事件](../../admin/admin/c-success-events/success-event.md)下查看事件类型。

* **计数器事件**：默认的事件设置。大多数事件是计数器事件。计算匹配自定义事件 `event1` - `event1000` 存在于 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中的点击数。
* **数字事件**：对 `events` 变量中分配给事件的数值求和。
* **货币事件**：将货币兑换与当日的汇率进行对比，然后对 `events` 变量中分配给每个点击的数值求和。

可用事件的数量取决于贵组织的 Analytics 合同。大多数使用非传统合同的组织具有 1000 个可用的自定义事件。如果您不确定有多少自定义事件可供使用，请与贵组织的客户经理联系。

Adobe 强烈建议您在贵组织的[解决方案设计文档](/help/implement/prepare/solution-design.md)中记录使用每个事件的方式。
