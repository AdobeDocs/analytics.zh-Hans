---
title: 次要实施审查（在每个网站发布后）
description: 按照以下步骤确保实施不出错并与KPI保持一致。
translation-type: tm+mt
source-git-commit: 82064e267729b6995402bd122c6f71b3d38967a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# 次要实施审查（在每个网站发布后）

为什么在每个网站发布后都应查看实施？ 因为您需要确保代码更新没有产生任何意外的后果，并且您应该在数据仍然很小时解决数据质量问题。 如果您在每个网站发布后一致地进行此次小评论，您会发现您的 [主评论](/help/implement/review/major-review.md) （每6个月一次）要容易得多。 您还将防止小问题发展成可能侵蚀利益相关者信心的大数据问题。

## 1.此版本对网站该部分的数据有何影响？

进行彻底的单元测试：查看与刚刚更新的站点部分对应的所有代码和变量，确保新跟踪能按设计方式工作。

## 2.更新您的文档

使用您添加／更改的任何变量更新您的业务需求文档(BRD)和解决方案设计参考(SDR)，以适应发布。

没有实施文档？ 导出一列表变量，并使用此模板创建您的BRD [或SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation)。

## 3.开始5大关键绩效指标

了解您的五大关键绩效指标(KPI)将帮助您确定您需要检查的相关指标和维度。 如果您在过去6个月中未刷新KPI，或您的企业尚未创建KPI，请按照以下 [说明操作](/help/implement/review/define-kpis.md)。

## 4.发布后，所有KPI指标和变量是否仍能正常工作？

请记住，任何代码更新都可能产生意想不到的后果。 您需要确保与前5个KPI关联的所 [有指标和维度](/help/implement/review/define-kpis.md) 仍能正常运行。 为此，请执行以下操作：

* **创建仪表板** ，查看这些关键指标和变量的每小时趋势视图。您还可以为每个指标设置智能预警)，并在一两天的发布后对其进行监控，以确保您获得所期望的数据，且数据正确。 寻找拐点。 准备立即纠正任何严重问题。 如果发现任何不正确的差异，请查看数据层、标签管理器规则和处理规则，找出原因。
* **重新运行Analytics运行状况仪表板** ，以监控KPI指标和变量的大趋势。
有关如何确保指标和变量正常工作的更多详细信息，请阅读Adobe Analytics冠军Sarah Owen的这些提示。

## 5.您的数据质量是否存在差距？

评估情况并制定修正数据的计划。 然后进行所需的更改，更新文档，并告知利益相关者您所做的更改。

观看Adobe Analytics冠军Sarah Owen的此视频，了解将实施评论融入繁忙计划的自然时刻：

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
