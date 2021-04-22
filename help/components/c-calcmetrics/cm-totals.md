---
title: 计算量度总计
description: 了解计算量度总计在不同 Analytics 工具中的差异
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '429'
ht-degree: 100%

---

# 计算量度总计

计算量度总计的显示方式在 [!DNL Reports & Analytics] 和 [!DNL Analysis Workspace] 中有所不同。此部分将阐述二者的具体差异。

## [!DNL Reports & Analytics] 中的计算量度总计

在 [!DNL Reports & Analytics] 中查看报表时，计算量度始终会在“总计”下方显示 `n/a`。因为所有计算量度都由用户定义，所以很多情况下，总计没有任何意义。请仔细研究下面的示例：

贵组织创建了计算量度 `orders` / `visits`，用于确定在您的网站上购买了产品的访问百分比。如果将此量度纳入产品报表，则多个产品会归于单次订购。而且，多个产品也会归于单次访问。如果将计算量度总计纳入此报表，则需要考虑以下问题：

| 问题 | 回答 |
|---|---|
| 汇总行项目是否有意义？ | 没有意义，因为单次订购中可能包含多个产品，而且单次访问中也可能包含多个产品。如果汇总行项目，则订购总数和访问总数会与实际订购总数和实际访问总数不匹配。 |
| 计算订购总数和访问总数是否有意义？ | 没有意义，因为总数与单个行项目的总和不匹配。此外，订购总数和访问总数都是单独计算的量度。 |

由于没有逻辑和具体的方法来确定计算量度在报表中是否有意义，因此将完全省略“总计”量度。如果想要获得总计，可以执行下列操作之一：

* 创建一个计算量度，其中包括要纳入的各个量度的总计版本。
* 创建一个可计划的数据提取报表。
* 在 [!DNL ReportBuilder] 中创建数据请求。
* 使用 [!DNL Analysis Workspace]（见下文）。

## [!DNL Analysis Workspace] 中的计算量度总计

在 Analysis Workspace 中查看数据时，大多数情况下都会显示计算量度总计。在某些情况下则无法提供“总计”，例如，当报表行采用混合格式（例如，小数和货币）时。

显示“总计”时，量度通常在服务器端进行计算，这意味着“总计”删除了重复量度（例如，访问或访客）。在某些情况下，计算量度是在客户端通过表行相加生成，这意味着“总计”不会删除重复量度（例如，访问或访客）。这种情况出现于：

* 当自由格式表中使用了[静态行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)，并且选择了&#x200B;**[!UICONTROL 显示为当前行的总和]**￼选项（默认）时。
* 在[圆环可视化图表](/help/analyze/analysis-workspace/visualizations/donut.md)中，这是为了使数字相加总和等于 100%。

有关 Analysis Workspace 中总计的更多信息，请访问 [Workspace 总计](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=zh-Hans#static-row-total)。
