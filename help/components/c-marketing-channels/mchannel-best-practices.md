---
title: 实施Adobe Analytics Marketing渠道的最佳实践
description: 更新了将营销渠道与Attribution IQ和Customer Journey Analytics结合使用的最佳实践
translation-type: tm+mt
source-git-commit: 402546c3110e78240e9379ea28957b070f22e697
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 3%

---


# 营销渠道Attribution IQ — 最佳实践

[营销](/help/components/c-marketing-channels/c-getting-started-mchannel.md) 渠道是Adobe Analytics的一个宝贵而强大的功能。当前关于营销渠道实施的指南是在既不存在[Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace)也不存在[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hans#cja-usecases)的时候制定的。

为了将来验证您的营销渠道实施，并确保报告与Attribution IQ和Customer Journey Analytics保持一致，我们发布了一组更新的最佳实践。 如果您已经在使用营销渠道，您可以在这些新准则中选择最佳选项。 如果您是营销渠道的新手，我们会建议您遵守所有新的最佳实践。

当营销渠道首次面世时，他们只提供了首次接触和最后接触维度。 在有了当前版本的归因后，不再需要显式的首次接触/最后接触维度。Adobe提供通用的“营销渠道”和“营销渠道详细信息”维度，以便您可以将其与所需的归因模型一起使用。 这些通用维度的行为与“最近接触渠道”维度相同，但标签也不同，以防止在使用具有不同归因模型的营销渠道时出现混淆。

由于营销渠道维度取决于传统的访问定义（由其处理规则定义），因此不能使用虚拟报表包更改其访问定义。 这些修订的做法使得具有Attribution IQ和CJA的清晰和受控的回顾窗口成为可能。

## 最佳实践#1:利用Attribution IQ实现受控分析

我们建议使用[Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace)代替现有的营销渠道归因来优化您的营销渠道分析。 遵循其他最佳做法，确保使用Attribution IQ对您的分析进行一致、可靠的控制。

![](assets/attribution.png)

* 营销渠道和营销渠道详细信息的维配置会根据每个营销渠道实例建立要评估的接触点。
* 对于量度分析，您的组织应根据一个或多个归因模型对齐。使用此模型保存自定义量度以便重复使用。
* 默认情况下，数据会使用“上次联系”和“访客参与期”的设置进行分配。 Attribution IQ量度模型优惠对回顾窗口的更大控制，以及更多种类，包括[ algorithmic attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html?lang=en#analysis-workspace)。

## 最佳实践#2:没有直接和会话刷新渠道定义

不建议使用直接和内部/会话刷新渠道与自定义归因模型(Attribution IQ)一起使用。

如果您的组织已配置了“直接”和“会话刷新”，该怎么办？ 在这种情况下，我们建议您为营销渠道创建分类，并将这两个渠道保留为未分类。 分类的维度将产生与从未配置这些渠道相同的Attribution IQ结果。

![](assets/direct-session-refresh.png)

## 最佳实践#3:为所有渠道启用“覆盖最近联系渠道”

启用此设置后，与Workspace中的“营销渠道”维度一起使用的自定义归因模型效果最佳。 启用此设置会导致在遇到新渠道/详细信息时计数营销渠道实例。 您应为除“直接”或“内部/会话刷新”(我们不再建议与自定义归因模型(Attribution IQ)一起使用)之外的所有渠道启用此选项。

![](assets/override.png)

## 最佳实践#4:最大限度地缩短访客参与时间

将“访客参与期”设置为“1天”最小值会最小化持续值的可能性。 由于自定义归因模型(AIQ)允许灵活的回顾窗口，因此我们建议设置最小值以最大限度地减少此设置的影响。

![](assets/expiration.png)

## 最佳实践#5:营销渠道处理规则应仅对启用的渠道存在

确保删除所有针对禁用渠道的营销渠道处理规则。 规则应仅对选中为已启用的营销渠道存在。
