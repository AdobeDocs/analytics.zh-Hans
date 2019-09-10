---
title: 计算量度总计
seo-title: 计算量度总计
description: 了解计算指标总数在Analytics工具中的差异
seo-description: 计算计算指标总数的方式
translation-type: tm+mt
source-git-commit: ec3187f1548aa107f03d9abf7ceacb7a4a85abb3

---


# 计算量度总计

计算得出的量度总数之间的差异不同 [!DNL Reports & Analytics] [!DNL Analysis Workspace]。本节将介绍不同之处。

## 计算得出的指标总数 [!DNL Reports & Analytics]

当您在中 [!DNL Reports & Analytics]查看报表时，计算得出的指标总是显示 `n/a` 在总计下方。由于所有计算指标都是用户定义的，所以在许多情况下，这一点没有意义。请仔细研究下面的示例：

您的组织已创建计算量度 `orders` / `visits` 用于确定在您的站点上购买了某些内容的访问百分比。如果您将此指标引入产品报告，则将多个产品归于一个订单。而且，几个产品被归因于一次访问。如果此报告中包含计算得出的量度总数，则会出现以下问题：

| 问题 | 回答 |
|---|---|
| 汇总行项目是否有意义？ | 事实并非如此，因为多个产品可以包含在一个订单中，而且多个产品可以包含在一次访问中。如果汇总了行项目，则总订单和总访问量将与实际的总订单和访问量不匹配。 |
| 获得总订单和访问总是有意义吗？ | 它不存在，因为总数与单个行项目的总和不匹配。此外，总订单和访问总是单独计算指标。 |

由于没有逻辑和可靠的方法来确定计算量度在报表中是否有意义，因此完全忽略量度总数。如果您要获得总计，则可以执行以下操作之一：

* 创建一个计算指标，其中包含您希望包含的量度的总版本。
* 创建可计划的数据提取报告。
* 在ReportBuilder中创建数据请求。
* 使用Analysis Workspace(见下文)。

## 计算得出的指标总数 [!DNL Analysis Workspace]

在Analysis Workspace中，在某些情况下，将计算计算得出的量度总数：

* 如果在自由表单表中有 [](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) 静态行，并 *[!UICONTROL 通过累加每个列]* 选项当前中的值(默认值)，则将计算总计。
* 在 [Dont可视化](/help/analyze/analysis-workspace/visualizations/donut.md)中。
* 在 [“摘要更改”可视化](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)中。
