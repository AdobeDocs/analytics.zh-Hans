---
title: 促销活动跟踪工作流
description: 使用Adobe Analytics跟踪您的营销工作。
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: c118d42667c4a1af55929834b87d148a5973bed9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# 促销活动跟踪工作流

如果贵组织希望跟踪营销工作的绩效和点进率，您可以使用以下流程。 下面的每个步骤都提供了包含更多详细信息的专述部分。

1. [建立跟踪代码生成过程](#establish-a-tracking-code-generation-process)
1. [将所需的跟踪代码添加到电子邮件](#add-the-desired-tracking-code-to-the-email)
1. [设置或调整Adobe Analytics实施以包含跟踪代码数据](#include-campaign-variables-in-your-implementation)
1. [在Analysis Workspace中查看报表](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) 可帮助简化每个步骤，以充分利用营销工作的价值。 有关更多信息，请联系您的Adobe销售代表。

## 建立跟踪代码生成过程

每个组织对跟踪代码的需求各不相同。 在手动创建的跟踪代码足以满足某些需求的情况下，某些组织可能只有最少的需求。 其他组织可能希望更好地控制跟踪，并且已设置多个系统以创建所需的跟踪代码。 如果贵组织除了使用Adobe Analytics之外还使用Google Analytics，则贵组织可能已经拥有 `utm` 已建立跟踪代码模型。

无论您选择如何创建或生成跟踪代码，在适当的系统中设置一致都可让您的组织在将跟踪代码分组以便进行报告时更加轻松。 始终如一的结构化跟踪代码允许您创建 [分类规则](/help/components/classifications/crb/classification-rule-builder.md) 以便对类别性能有洞察。

## 将所需的跟踪代码添加到URL

获得所需的跟踪代码值后，您可以将其添加到您在线发布的任何链接，如广告、社交媒体或电子邮件。 添加这些跟踪代码通常会在链接的查询字符串中进行。 您使用的查询字符串参数取决于贵组织的跟踪要求；常见的查询字符串参数是 `cid` （促销活动ID的简称）。 某些同时使用Google Analytics的组织可能已经拥有多个促销活动查询字符串参数，例如 `utm_source`, `utm_medium`，等等。

向电子邮件中的链接添加查询字符串类似于以下内容：

```text
https://example.com?cid=EM989027
```

## 在实施中包含促销活动变量

Adobe Analytics [跟踪代码](/help/components/dimensions/tracking-code.md) 维度。 但是，不同的组织可能有不同的跟踪要求。 引用贵组织的 [解决方案设计文档](../prepare/solution-design.md) 以便始终跟踪正确变量中的正确值。

如果贵组织尚未设置促销活动跟踪，则可以调整实施以设置 [`campaign`](/help/implement/vars/page-vars/campaign.md) 变量。 请参阅 [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) 方法以了解如何收集特定于贵组织实施的查询字符串参数值。

如果贵组织收集 `utm` 查询字符串中，您可以选择以下任一方式：

* 发送全部 `utm` 将查询字符串作为连接值添加到“跟踪代码”维度中。 然后，您可以使用 [分类规则](/help/components/classifications/crb/classification-rule-builder.md) 以创建更多关注每个 `utm` 参数。 此方法的学习曲线比较复杂，但不使用任何额外的eVar。
* 发送每个 `utm` 将查询字符串转换为单独的 [eVar](/help/components/dimensions/evar.md). 此方法总体实施更为简单，但需要使用额外的eVar。

## 在Analysis Workspace中查看报表

正确设置实施以收集跟踪代码数据后，即可在Analysis Workspace中查看报表。

1. 登录到 [Adobe Experience Cloud](https://experience.adobe.com) 选择 [!UICONTROL Adobe Analytics].
1. 创建 [工作区项目](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. 在左侧的组件列表中，将 [跟踪代码](/help/components/dimensions/tracking-code.md) 维度添加到工作区画布。
1. 拖动所需的量度，例如 [访问次数](/help/components/metrics/visits.md) 或 [订单数](/help/components/metrics/orders.md) 到工作区画布的右侧。

![促销活动跟踪报告](../assets/campaign-tracking-report.png)
