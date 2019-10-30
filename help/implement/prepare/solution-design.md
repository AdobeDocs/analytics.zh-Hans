---
title: 创建解决方案设计文档
seo-title: 创建解决方案设计文档
description: 了解解决方案设计文档是什么，以及如何在组织中使用它。
seo-description: 了解解决方案设计文档是什么，以及如何在组织中使用它。
translation-type: ht
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 创建解决方案设计文档

解决方案设计文档（也称为解决方案设计参考或业务需求文档）实质上是 Analytics 实施的蓝图。它定义了整个组织中由利益相关方确定的标准，并将这些标准转换为 Adobe Analytics 中的变量。如果没有这些变量，组织将很难协调报告需求，而且往往无法收集重要的数据。

## 先决条件

[验证 Analytics 实施并发布到生产环境](../implement-with-launch/validate-publish-prod.md) - 虽然没有直接要求，但 Adobe 建议实现一个基本实施，以便在建立和实施其他业务需求的同时收集关键数据。

## 设计文档的所有权和存放位置

* **确定贵组织中负责维护解决方案设计文档的人员。**&#x200B;这个角色可以是个人，也可以是团队。确保始终维护解决方案设计，即便角色更改或组织重组也是如此。这是一份动态文档，必须妥善维护。
* **确定解决方案文档的存放位置。**&#x200B;解决方案设计文档并没有单一的最佳存放位置，但它们通常被存放在可广泛访问的内部位置。例如，共享电子表格或协作工作区（如 SharePoint 或内部 Wiki）。它不需要对每个人都可编辑，但这对那些能够访问报表的人来说是有益的，因为他们至少能够查看这份文档。

## 定义业务需求

在确定要收集的数据时，最简单的说法就是“所有数据”，但所收集的这些数据很快就会变得难以管理，而且其价值甚至比收集更简洁数据所提供的价值更低。

1. **确定关键绩效指标。**&#x200B;您最终希望访客做什么？这个问题的答案因行业和垂直情况而异，并且可能会有多种答案。例如，购买、注册或广告点击。
1. **找出要收集的最重要的数据。**&#x200B;提出您希望得到具体答案的业务问题。这些问题的答案将会为您提供有关如何改进 KPI 的见解。
1. **回答这些问题并确定您的跟踪需求。**&#x200B;按维度和量度对这些需求进行分组。
   * 维度是包含文本的变量。例如，内部搜索词、产品类别或访客所点击区域的名称。
   * 量度是您希望访客执行的特定事件 - 当访客执行您希望他们执行的操作时，数字就会增加 1。例如，提交订单、订阅新闻稿或提交调查答复。
1. **将维度和量度映射到某个页面或电子表格中。**&#x200B;该页面或表格最终将变成您的解决方案设计文档。一些有用的列或要点包括：
   * 实施状态：已计划、活动、不活动、问题等。如果已实施，或者出现数据收集问题，其会将变量的状态告知文档查看者。
   * 变量名称：例如“内部搜索词”。此值就是分析人员在 Analytics 中工作时会看到的内容。
   * 映射到的 Analytics 变量：您选择为其分配值的默认或自定义 Analytics 变量。维度通常属于 eVar，而量度则属于事件。
   * 逻辑：描述变量的设置方式以及决定其值的因素。例如，“仅在内部搜索页面上设置。获取 q 查询字符串参数的值。”
   * 您要包含的与变量相关的任何其他注释

## 其他资源

定义解决方案设计文档是一个相当复杂的项目，尤其是对于以前从未创建过此类文档的组织而言。如果需要其他帮助，Adobe 将会为您提供专门的咨询服务，以帮助贵组织启动并运行 Adobe Analytics。如果希望获得 Adobe 的专业服务，请与您的客户经理联系。您可以填写一份[技术实施前调查问卷](assets/technical-pre-implementation-questionnaire.pdf)，以便 Adobe 知道如何根据贵组织的需求提供帮助。

另外还有一些 Adobe 合作伙伴专门负责帮助创建解决方案设计文档，以及在您的网站上实施 Adobe Analytics。

> [!NOTE] 尽管 Analytics 社区成员发现以下链接很有帮助，但这些链接并不归 Adobe 所有。查看其内容时，请注意这一点。

* [设置 Web Analytics 解决方案设计的 7 个步骤](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance)，由 ObservePoint 提供
* [数字分析流程框架](https://analyticsdemystified.com/cn/analytics-strategy/framework-digital-analytics-process/)，由 Analytics Demystified 提供
* [解决方案设计参考实际上是您的 BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/)，由 Numeric Analytics 提供
* [如何制作 Adobe Analytics 标记图](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/)，由 Antti Koski 提供
* [解决方案设计文档的重要性](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document)，由 Ebiquity 提供

## 后续步骤

在解决方案设计文档中实施变量。

* eVar 简介：了解 eVar 是什么、其工作方式以及如何在实施中使用
* 事件简介：了解成功事件是什么、其工作方式以及如何在实施中使用
