---
title: 在Analysis Workspace中创建基本报告
description: 了解如何在Analysis Workspace中以适合熟悉Google Analytics等第三方工具的用户的格式创建基本报告。
translation-type: tm+mt
source-git-commit: 099662d021c1919f0760e79154536cfd0e23e959

---


# 在Analysis Workspace中为Google Analytics用户创建基本报告

Analysis Workspace（Adobe Analytics中的主要功能之一）为用户提供了一个强大的区域，可让用户了解所收集的数据。 Google Analytics和Adobe Analytics之间的报告非常不同：

* Google Analytics中的报告结构允许您选择特定类型的数据，如地理位置或引用流量。 该平台使用基于预期最佳数据查看方式的预制报告视图。
* Analysis Workspace中的报表结构提供了空白画布，在满足准确报表需求方面提供了更大的灵活性。

由于Analysis Workspace的工作方式与预制报表更像画布，因此从Google Analytics重新创建报表只是使用正确的可视化和组件的问题。

## Workspace中使用的关键术语

* **面板** ，是工作区的总体构件。 在几乎所有情况下，都会使用自由格式面板。
* **可视化** ，由所有自由形式面板组成。 其目的是以不同格式表示数据。 大多数情况下，该格式是表格，但有些时候可能是圆环图或折线图。 Google Analytics中的许多报告都由两种可视化功能构成：折线图和自由格式表。
* **组件** （组件）放在可视化中以返回数据。 组件可以通过多种不同的方式混合，以满足报告需求。
   * **尺寸** 是变量值，通常包含文本。 示例包括页面名称、引用或地理国家／地区。 它们通常作为表中的行列出。
   * **度量** 通常表示某种事件或某种类型的转换。 例如，常见事件（如页面查看）或更重要的事件（如购买或注册）。 它们通常被视为表中的列，以显示每个维发生事件的次数。
   * **区段** 是数据的子集，其行为与Google Analytics中的区段类似。 它们允许您制作自定义的过滤器，使您能够专注于数据的特定部分。
   * **日期范围** ，允许您按事件发生时间组织数据。 它们是长期观看趋势的支柱，通常与指标配对。

## 在Workspace中创建基本报告

通过将正确的组件拖动到工作区画布上，创建“所有页面”报表（与Google Analytics中的报表类似）。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
1. 在顶部导航栏中，单击“工作区”。
1. 单击“新建项目”按钮。
1. 在模态弹出窗口中，确保选择“空白项目”，然后单击“创建”。
1. 在左侧，将显示维度、量度、区段和日期范围列表。 找到页面维度（橙色），并将其拖动到标有“将维度放在此处”的画布上。
1. 可查看显示本月最热门页面的报告。 Analysis Workspace automatically populates the report with the [Occurrences](/help/components/c-variables/c-metrics/metrics-occurrences.md) metric.
1. Google Analytics中的表通常包含7-8个指标。 找到“弹出率”量度（绿色），并将其拖动到“发生次数”量度标题旁边。 如果将“弹出率”量度拖动到“发生次数”旁边，则两个量度将并排显示。
1. 通过将度量拖动到现有度量标题旁边，可以并排放置许多度量。 有关 [如何获取Google Analytics中通常使用的指标](common-metrics.md) ，请参阅常用的指标。

   ![新指标](/help/technotes/ga-to-aa/assets/new_metric.png)

## 从Workspace中预建的报告模板开始

通过访问项目模板创建内容消耗模板（与Google Analytics中的“所有页面”报表类似）。

1. 单击“新建项目”按钮。
1. 找到并双击“所有模板”下列出的“内容使用(Web)”图标。
1. 浏览已预建的每个可视化：“登入页面流”、“顶级页面”表、“退出页面流”、“登入站点区域流”和“顶级站点区域”表。

   ![模板选择](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## 试用该工具

由于 Analysis Workspace 是一款报表工具，因此不会对数据收集产生任何影响。您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。将不同的维度和量度组合拖动到工作区项目中，可查看相应的效果。

如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。You can also start with a clean slate by clicking *[!UICONTROL Project]>[!UICONTROL New]*in the upper left menu.

Adobe在Analysis Workspace的右键单击上下文菜单中提供了许多功能。 大多数可视化和组件都可以右键单击，以便进行更详细的分析和交互。 请考虑在工作区中右键单击组件以查看哪些选项可用。

## 了解要使用的维度和指标

如果您熟悉Analysis Workspace，并且希望重新创建通常在Google Analytics中查看的特定报表，请在相应的页面上找到该报表：

* [实时报表](realtime-reports.md)
* [受众报告](audience-reports.md)
* [客户获取报告](acquisition-reports.md)
* [行为报告](behavior-reports.md)
* [转换报告](conversions-reports.md)
