---
title: 营销活动跟踪工作流程
description: 使用 Adobe Analytics 跟踪您的营销工作。
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 100%

---

# 营销活动跟踪工作流程

如果您的组织要跟踪营销工作的表现和点进率，可使用以下过程。其中每个步骤在下方都有一个对应的部分，其中包含更多详细信息。

1. [建立跟踪代码生成过程](#establish-a-tracking-code-generation-process)
1. [将所需的跟踪代码添加到电子邮件](#add-the-desired-tracking-code-to-the-email)
1. [设置或调整您的 Adobe Analytics 实施以使其加入跟踪代码数据](#include-campaign-variables-in-your-implementation)
1. [在 Analysis Workspace 中查看报告](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/cn/products/campaign/adobe-campaign.html) 可帮助简化其中每个步骤，以使您的营销工作发挥最大作用。有关更多信息，请与您的 Adobe 销售代表联系。

## 建立跟踪代码生成过程

每个组织对跟踪代码的需求不尽相同。某些组织可能只有少量需求，这样手动创建跟踪代码即可。其他组织可能要强化对跟踪的控制，并准备了多个系统用于创建所需的跟踪代码。如果您的组织除了使用 Adobe Analytics 之外还使用 Google Analytics，则您的组织可能已建立了 `utm` 跟踪代码模型。

无论您决定如何创建或生成跟踪代码，通过备妥一致的系统，在您要将跟踪代码组合在一起以供报告时，您的组织均可事半功倍。通过结构一致的跟踪代码，您可创建[分类规则](/help/components/classifications/crb/classification-rule-builder.md)，以使您可了解分门别类的表现。

## 将所需的跟踪代码添加到 URL

一旦获得所需的跟踪代码值，即可将它添加到您发布到网上的任何链接，如广告、社交媒体或电子邮件。一般在链接的查询字符串中添加这些跟踪代码。您使用哪个查询字符串参数取决于您组织的跟踪要求；一个常见的查询字符串参数是 `cid`（营销活动 ID 的缩写）。某些还使用 Google Analytics 的组织可能已有多个营销活动查询字符串参数，如 `utm_source`、`utm_medium` 等。

将查询字符串添加到电子邮件中的链接看上去将类似于这样：

```text
https://example.com?cid=EM989027
```

## 在实施中加入营销活动变量

Adobe Analytics 有一个专用的[跟踪代码](/help/components/dimensions/tracking-code.md)维度，您可使用它衡量组织内的各种营销工作。但是，不同的组织可能有不同的跟踪要求。参考组织的[解决方案设计文档](../prepare/solution-design.md)，以始终跟踪正确变量中的正确值，这一点非常重要。

如果您的组织尚未设置营销活动跟踪，则您可调整您的实施以设置 [`campaign`](/help/implement/vars/page-vars/campaign.md) 变量。请参阅 [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) 方法以了解如何收集您组织的实施特有的查询字符串参数值。

如果您的组织收集 `utm` 查询字符串，则可选择：

* 将所有 `utm` 查询字符串作为串联值发送到“跟踪代码”维度。然后，可使用[分类规则](/help/components/classifications/crb/classification-rule-builder.md)创建重点关注每个 `utm` 参数的其他维度。此方法略显难学，但不使用任何额外的 eVar。
* 将每个 `utm` 查询字符串发送到一个单独的 [eVar](/help/components/dimensions/evar.md) 中。此方法总体上更易于实现，但需要使用额外的 eVar。

## 在 Analysis Workspace 中查看报告

正确设置实施以收集跟踪代码数据后，您可以在 Analysis Workspace 中查看报告。

1. 登录到 [Adobe Experience Cloud](https://experience.adobe.com) 并选择 [!UICONTROL Adobe Analytics]。
1. 创建 [Workspace 项目](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)。
1. 在左侧的组件列表中，将[跟踪代码](/help/components/dimensions/tracking-code.md)维度拖动到工作区画布。
1. 将[访问次数](/help/components/metrics/visits.md)或[订单数](/help/components/metrics/orders.md)等所需的指标拖至工作区画布的右侧。

![营销活动跟踪报告](../assets/campaign-tracking-report.png)
