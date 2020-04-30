---
description: 营销渠道概述报表旨在提供概要性的分析，帮助您确定哪些方法最能吸引客户访问您的网站。使用此报表可将成功量度和收入分配到各种不同渠道。您还可以查看每个渠道中最成功的具体促销活动或关键词。它包含自己的独特直观界面，让您可以同时查看首次联系和最近联系量度。
title: 营销渠道概述
topic: Reports
uuid: e4542014-2098-4f4a-ac0d-97587182d6cc
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 营销渠道概述

营销渠道概述报表旨在提供概要性的分析，帮助您确定哪些方法最能吸引客户访问您的网站。使用此报表可将成功量度和收入分配到各种不同渠道。您还可以查看每个渠道中最成功的具体促销活动或关键词。它包含自己的独特直观界面，让您可以同时查看首次联系和最近联系量度。

## 常规属性 {#section_87F54048CE5445F7A6C795C7787C530A}

* 此报表完全依赖于营销渠道[处理规则](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-channels-rules.html)。更改这些规则会更改报表中数据的计算方式。
* 处理规则的顺序对于营销渠道的运行及作用十分重要。针对每次访问，都会先检查处理规则最上方的第一条标准，然后依次向下逐条过滤。
* 此报表由两部分构成：渠道本身及渠道详细信息。单击每个渠道旁边的“+”按钮可显示其详细信息。
* 每列只能添加四个量度。但对于您可以使用的列数并无限制。
* 在最后一列的末尾处可看到一条小的趋势线。该趋势线可以在活动量度之间循环切换。
* 除了按标准方法收集的多种渠道之外，您还可以使用离线数据源。
* 可以使用[分类](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html)来重命名和整合行项目。
* 可在此报表中使用以下量度（取决于组织和报表包设置）：

   * **点进次数**：定义 *`s.campaign`* 变量的次数。
   * [新参与](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-new-engagements.html)：接收到新的“首个联系渠道”的访客人数。
   * 所有标准电子商务量度：收入、订购、件数、购物车、购物车查看、结账、购物车加货、购物车减货。
   * 所有自定义事件：事件 1-80、事件 81-100（使用 H22 代码或更高版本的代码时）。
   * **访问**&#x200B;和&#x200B;**访客**：需要商务访问和访客（取决于组织和报表包）。请联系您的客户经理以了解详细信息。
   * **预算**&#x200B;和&#x200B;**成本**：营销渠道特定的量度。请参阅[成本和预算](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/analyze-mc.html)。

## 产品特定的属性 {#section_0C78D294D00942FD9A26D37CB5D645AE}

**版本 14 和 15**

此报告可通过转到>( **[!UICONTROL Marketing Channels]** 前提 **[!UICONTROL Channel Overview Report]** 是菜单未自定义)访问。

此报表无法使用区段，请改 [!UICONTROL First- or Last-Touch Channel] 用或 [!UICONTROL First- or Last-Touch Details] 报告。

**Ad Hoc Analysis**

Though the [!UICONTROL Marketing Channel Overview Report] is not available, Marketing Channel reports can be accessed with metrics using different allocation. 这样您就可以有效地重新创建一个非常类似的报表。

此报表可使用多个高级区段。
