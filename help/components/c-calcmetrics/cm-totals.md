---
title: 计算量度总计
description: 了解Analytics工具中计算的指标总数有何不同
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 计算量度总计

计算量度总数的显示方式在与之间 [!DNL Reports & Analytics] 不同 [!DNL Analysis Workspace]。 本节将解释这些差异。

## 计算量度总数 [!DNL Reports & Analytics]

查看报告时，计 [!DNL Reports & Analytics]算的量度始终显示 `n/a` 在总数下。 由于所有计算的指标都由用户定义，因此在很多情况下，这一总数并不合理。 请仔细研究下面的示例：

您的组织已经创建了计算量 `orders` 度/ `visits` 以确定在您的网站上购买内容的访问量百分比。 如果将此指标纳入产品报表，则多个产品将归因于单个订单。 而且，多个产品归因于一次访问。 如果此报告中包含计算的度量总数，则会出现以下问题：

| 问题 | 回答 |
|---|---|
| 对这些行项进行总和是否有意义？ | 它没有，因为一个订单中可以包含多个产品，而一次访问中可以包含多个产品。 如果汇总了行项目，则订单总数和访问总数与实际订单总数和访问总数不匹配。 |
| 接受总订单和总访问量是否合理？ | 它不匹配，因为总数与单个行项目的总和不匹配。 此外，订单总数和访问总数将单独计算指标。 |

由于没有逻辑和具体的方法来确定计算的度量在报告中是否合理，因此将忽略度量总数。 如果要获得总计，您可以执行下列操作之一：

* 创建一个计算量度，其中包括您要包含的量度的总版本。
* 创建可计划的数据提取报告。
* Create a data request within [!DNL ReportBuilder].
* 使 [!DNL Analysis Workspace] 用（见下文）。

## 计算的量度总数 [!DNL Analysis Workspace]

在Analysis Workspace中查看数据时，大多数情况下都会显示计算的度量总数。 在某些情况下，无法提供总数，例如当报表的行采用混合格式（如小数和货币）时。

显示总数时，通常在服务器端计算，这意味着总数可以消除重复的指标，如访问或访客。 在某些情况下，计算的度量通过表各行的总和在客户端生成，这意味着总和不会消除重复的度量，如访问或访客。 出现这种情况：

* 当自 [由格式表中使用](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) static行时，将选 **[!UICONTROL 中“显示为当前行的和”选项]** （默认）。
* 在甜 [圈可视化中](/help/analyze/analysis-workspace/visualizations/donut.md)，这个数字加起来高达100%。
