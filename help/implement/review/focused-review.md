---
title: 重点审查（每个网站发布后）
description: 按照以下步骤操作以确保您的实施无误并与 KPI 保持一致。
translation-type: tm+mt
source-git-commit: 912e5077889a02c3bf0dea9b079d213bb20f9424
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 86%

---


# 重点审查（每个网站发布后）

为何要每几个月审查一次您的实施？这样您可以在数据存在的任何质量问题还是小问题时解决它们。如果您在每个网站发布后都能坚持进行这种“重点审查”，您会发现一年两次的[全面审查](/help/implement/review/full-review.md)会更加容易。您还将防止小问题演变成可能会削弱利益相关者信心的大数据问题。

## 1.开始5大关键绩效指标

了解您的 5 项 关键绩效指标 (KPI)，将有助于确定您需要检查的相关量度和维度。如果您在过去 6 个月内未刷新 KPI，或者如果您的企业尚未创建 KPI，请按照[这些说明](/help/implement/review/define-kpis.md)操作。

## 2.确保您的KPI指标和变量仍能正常运行

请记住，随着时间的推移，代码更新可能会产生意想不到的结果。您需要确保与 [5 大 KPI](/help/implement/review/define-kpis.md) 相关的所有指标和维度仍然正常运行。理想情况下，此操作应在网站发布后立即执行；如果您在最近几个月内未执行此操作，请&#x200B;*立即*&#x200B;执行。请按以下步骤执行此操作：

* 创建仪表板以查看这些关键指标和变量的每小时趋势视图（或为每个指标设置[智能警报](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace)）。 然后，对其进行一到两天的监控，确保您能获得所需数据，且数据正确。寻找拐点。准备好立即纠正任何严重问题。如果发现任何误差，请查看数据层、标签管理器规则及处理规则，并找出原因。
* 重新运行 [Analytics 运行状况功能板](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)，以监控 KPI 量度和变量的总体趋势。

*有关如何确保量度和变量正常工作的更多详细信息，[请参阅 ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608)Adobe Analytics 冠军 Sarah Owen 给出的这些提示。*

## 3.深入检查站点更新部分的数据

确保最新的网站版本不会对该网站区域的数据收集产生不利影响：审查与该区域对应的所有代码和变量，确保新跟踪按计划运行。

## 4.更新您的文档

如果您最近添加或更改了任何量度或变量，您需要更新业务需求文档 (BRD) 和解决方案设计参考 (SDR)。

如果您没有实施文档，请导出一个变量列表，并使用[此模板](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=zh-Hans#implementation)创建 BRD 或 SDR。

## 5.立即解决您在数据质量方面发现的任何差距

评估情况并制定数据修正计划。然后，进行所需更改并更新文档，同时将您所做的更改告知利益相关者。

*观看这段来自 Adobe Analytics 冠军 Sarah Owen 的 2 分钟视频，了解在繁琐的工作中进行实施审查的适当时间：*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
