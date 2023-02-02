---
title: 归因最佳实践
description: 确定归因模型的最佳实践是什么？
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 58%

---

# 归因最佳实践

为您的组织选择适合的归因模型取决于许多考虑因素。本文探讨了一种方法论和一些通用的最佳实践。

## 步骤 1：探索性分析

>[!NOTE]
>此分析需要在您选择归因模型之前进行。

此阶段最初包括了解客户行为和定义转化量度。根据转化量度，[数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=zh-Hans)（针对原始数据）或 Analysis Workspace 等工具可以帮助您更好地理解：

* 转化前接触不同营销渠道的客户数量
* 这些行为的比例/分布

例如，如果 50% 的客户在转化前接触了 3 个渠道，这 3 个渠道之间有什么互动吗？然后，您可以进行漏斗上层和漏斗下层分析以扩展您的理解。

### 漏斗上层分析

上漏斗分析渠道用于提升品牌或产品知名度。 例如，大部分电视广告的目标是品牌意识。您可能使用[“时间衰减”归因模型](/help/analyze/analysis-workspace/attribution/models.md)，因为随着时间的推移，人们会忘记您的电视广告。

### 漏斗下层分析

在漏斗较低的分析中，假设用户已经了解您的品牌并希望他们进行转化。 使用电子邮件、推送通知或Facebook广告。

## 步骤 2：基于规则的归因

此步骤的目的是验证您的假设。

**示例 1**

假设你的假设是：“与最近联系渠道相比，我的首次联系渠道对转化的影响更大。”

在这种情况下，您将使用 [“逆J型”归因模型](/help/analyze/analysis-workspace/attribution/models.md) 来检验这个假设。 此模型将 60% 的点数分给第一个接触点。

**示例 2**

假设你的假设是：“在我们的行业（如旅游行业），归因时间范围是60天或90天，而不是30天，因为客户在购买产品之前会进行大量研究。”

在这种情况下，您会更改 [回顾窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html#lookback-windows?lang=zh-Hans) 90天。

## 步骤 3：使用算法归因

如果您还没有一个归因模型来为所有问题提供令人满意的答案，则可以使用 [算法归因](/help/analyze/analysis-workspace/attribution/algorithmic.md). 由于很难验证大量可能的假设和组合，因此算法归因会使用内置算法来跨维度项目分配点数。

## 其他注意事项

* 您可能需要使用数据科学家的服务，而不是仅仅依靠 Analysis Workspace。
* 您可以依赖原始数据，就像在 Adobe 数据馈送中一样。
* 例如，如果您需要考虑展示数据，则可考虑使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans)。
