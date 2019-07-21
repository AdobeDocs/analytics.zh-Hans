---
title: 创建解决方案设计文档
seo-title: 创建解决方案设计文档
description: 了解解决方案设计文档的内容以及如何在组织中使用它。
seo-description: 了解解决方案设计文档的内容以及如何在组织中使用它。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 创建解决方案设计文档

解决方案设计文档(也称为解决方案设计参考或业务需求文档)本质上是分析实施的蓝图。它定义了整个组织中利益相关者确定的标准，并将其翻译为Adobe Analytics中的变量。如果没有一个组织，组织就会很难协调报告需求，往往会错过收集重要数据的时间。

## 先决条件

[验证您的Analytics实施和发布到生产](../implement-with-launch/validate-publish-prod.md) -尽管不是直接需要，但Adobe建议您实施基本实施，以便在建立和实施其他业务需求时收集关键数据。

## 设计文档的所有权和位置

* **确定组织中的谁负责维护解决方案设计文档。** 此角色可以是个人或团队。确保即使通过角色更改或组织重构来保留解决方案设计。它是一个生活文档，必须妥善维护。
* **确定解决方案文档的存放位置。** 解决方案设计文档没有单一最佳位置，但通常居住在可访问的内部位置。示例包括共享电子表格或协作工作区(如SharePoint或内部维基百科)。它不需要对每个人都可编辑，但对于可以访问报表的用户来说，这一点非常有用。

## 定义业务需求

在确定要收集的数据时，很容易说“一切”，但是可以快速变得不易管理，甚至可以比收集更简洁的数据量提供更少的价值。

1. **确定关键绩效指标。** 您最终希望访客做什么？这个问题的答案因行业和垂直而异，可能是多项内容。例如购买、注册或广告点击。
1. **找到最重要的收集数据。** 询问您希望特定答案的业务问题。这些问题的答案将提供有关如何改进KPI的洞察。
1. **进行这些问题并确定跟踪需求。** 将它们分为维度和指标。
   * 维度是包含文本的变量。示例包括内部搜索词、产品类别或访客单击的区域名称。
   * 量度是您希望访客执行的特定活动-执行所需操作时，数字会递增一次。示例包括提交订单、订阅新闻稿或提交调查答复。
1. **将维度和指标映射到页面或电子表格中。** 此页面或表格最终成为您的解决方案设计文档。一些有用的列或项目符号要点包括：
   * 实施状态：计划、活动、非活动、问题等。这会向查看器通知文档的状态(如果已实施)，或者如果数据收集存在问题。
   * 变量名称：例如，“内部搜索词”。此值将是分析师在Analytics中工作时看到的内容。
   * 分析变量映射到：您选择为其分配值的默认或自定义Analytics变量。维度通常属于eVar，而指标则归入事件之下。
   * 逻辑：描述变量的设置方式及其值。例如，“仅在内部搜索页面上设置。获取q查询字符串参数的值”。
   * 您希望包含的任何其他备注

## 其他资源

定义解决方案设计文档是一个相当复杂的项目，对于尚未创建过的组织尤为如此。如果需要额外的协助，Adobe会提供专门的咨询，帮助您的组织使用Adobe Analytics。如果要注册Adobe的专业服务，请与您的客户经理联系。A [Technical pre-implementation questionnaire](assets/technical-pre-implementation-questionnaire.pdf) can be filled out so Adobe knows exactly how to help based on your organization's needs.

还有一些Adobe合作伙伴专门致力于帮助创建解决方案设计文档，以及在您的网站上实施Adobe Analytics。

> [!NOTE] 尽管Analytics社区成员发现以下链接有用，但并非Adobe拥有。查看其内容时，请考虑此备注。

* [通过SocialPoint设置Web Analytics解决方案设计](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) 的个步骤
* [由Analytics Demystified打造的数字分析流程](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) 框架
* [解决方案设计参考实际上是由数字分析提供的BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/)
* [如何通过Anti Koski制作Adobe Analytics标记地图](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/)
* [解决方案设计文档](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) 的重要性，由Ebiquity提供

## 后续步骤

在解决方案设计文档中实现变量。

* eVar简介：了解eVar是什么、它如何工作以及如何在实施中使用它
* 活动简介：了解成功事件是什么、它如何工作以及如何在实施中使用它
