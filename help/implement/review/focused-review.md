---
title: 集中审阅（每个网站发布后）
description: 按照以下步骤确保实施不出错并与KPI保持一致。
translation-type: tm+mt
source-git-commit: a7f1da79bd5a6f78ed1a706ccae01b03a2f5665c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---


# 集中审阅（每个网站发布后）

您为何应每几个月检查一次实施？ 因此，您可以在数据质量仍然较小时解决任何数据质量问题。 如果您在每个网站发布后都一致地进行集中审阅，您会发现每两年[一次的完整审阅](/help/implement/review/full-review.md)要容易得多。 您还将防止小问题发展成可能侵蚀利益相关者信心的大数据问题。

## 1.开始您的前5个KPI

了解您的五大关键绩效指标(KPI)将帮助您确定您需要检查的相关指标和维度。 如果您在过去6个月中未刷新KPI，或者您的企业尚未创建KPI，请按照[这些说明](/help/implement/review/define-kpis.md)操作。

## 2.确保您的KPI指标和变量仍能正常运行。

请记住，随着时间的推移，代码更新可能会产生意想不到的后果。 您需要确保与[您的前5个KPI](/help/implement/review/define-kpis.md)关联的所有指标和维度仍然正常运行。 理想情况下，应在网站发布后立即执行此操作；如果您最近几个月没有这样做，请&#x200B;*now*。 为此，请执行以下操作：

* **创** 建仪表板以查看这些关键指标和变量的每小时趋势视图。您还可以为每个指标设置智能警报，并监视一两天，以确保您获得所期望的数据，且数据正确。寻找拐点。 准备立即纠正任何严重问题。 如果发现任何差异，请查看数据层、标签管理器规则和处理规则，找出原因。
* **重新运行Analytics Health Dashboard,** 以监控KPI指标和变量的大趋势。

有关如何确保您的指标和变量正常工作的更多详细信息，请阅读Adobe Analytics冠军Sarah Owen的[提示。](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608)

## 3.彻底检查站点更新部分的数据。

确保最近发布的站点版本不会对站点的该部分的数据收集产生不利影响：查看与该部分对应的所有代码和变量，确保新跟踪按设计方式运行。

## 4.更新您的文档。

如果您最近添加或更改了任何指标或变量，您需要更新业务需求文档(BRD)和解决方案设计参考(SDR)。

如果您没有实施文档，请导出一列表变量，然后使用[此模板](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation)创建BRD或SDR。

## 5.立即解决您在数据质量方面发现的任何差距。

评估情况并制定修正数据的计划。 然后进行所需的更改，更新文档，并告知利益相关者您所做的更改。

*观看Adobe Analytics冠军Sarah Owen的这段2分钟视频，了解将实施评论融入繁忙计划的自然时刻：*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
