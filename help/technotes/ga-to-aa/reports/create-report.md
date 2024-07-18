---
title: 在 Analysis Workspace 中创建基本报表
description: 了解如何在 Analysis Workspace 中以某种格式创建基本报表，适用于熟悉 Google Analytics 等第三方工具的用户。
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 100%

---

# 在 Analysis Workspace 中为 Google Analytics 用户创建基本报表

Analysis Workspace（Adobe Analytics 中的主要功能之一）为用户提供了一个功能强大的区域，可以了解所收集的数据。Google Analytics 和 Adobe Analytics 之间的报表差异极大。

* Google Analytics 中的报表结构允许您选择特定类型的数据，如地理位置或反向链接流量。该平台使用基于预期最佳数据查看方式的预制报告视图。
* Analysis Workspace 中的报表结构提供了空白画布，在满足准确报表需求方面提供了更大的灵活性。

由于 Analysis Workspace 的工作方式比预制报表更像画布，因此从 Google Analytics 重新创建报表只需使用正确的可视化和组件即可。

## 工作区中使用的关键术语

* **面板**&#x200B;是工作区的拱形构件块。几乎所有情况下，都会使用“自由格式”面板。
* **可视化**&#x200B;构成了所有自由格式面板。其目的是以不同格式表示数据。大多数情况下，该格式是表格，但有些时候可能是圆环图或折线图等。Google Analytics 中的许多报表由两个与可视化相当的功能构成：折线图和自由格式表。
* **组件**&#x200B;放置在可视化中，用来返回数据。组件可以通过多种不同的方式混合使用，以满足各种报告需求。
   * **维度**&#x200B;是变量值，通常包含文本。示例包括页面名称、反向链接或地理国家/地区。维度通常作为表中的行列出。
   * **指标**&#x200B;通常表示某种类型的事件或转化。示例包括一些常见事件（如页面查看）或比较重要的事件（如购买或注册）。指标最常见的是作为表中的列，用来显示每个维度发生的事件数。
   * **区段**&#x200B;是数据的子集，其行为与 Google Analytics 中的区段类似。允许您制作自定义过滤器，使您能够专注于数据的特定部分。
   * **日期范围**&#x200B;允许您按事件发生时间组织数据。日期范围是长期观察趋势的支柱，通常与指标结合使用。

## 在工作区中创建基本报表

通过将正确的组件拖动到工作区画布上，创建“所有页面”报表（与 Google Analytics 中的报表类似）。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
1. 在顶部导航栏中，单击“工作区”。
1. 单击“新建项目”按钮。
1. 在模态弹出窗口中，确保选择“空白项目”，然后单击“创建”。
1. 在左侧，将显示维度、指标、区段和日期范围列表。找到“页面”维度（橙色），并将其拖动到标有“在此处放置维度”的画布上。
1. 此时可以看到显示本月排名最前的页面的报表。Analysis Workspace 会自动使用[发生次数](/help/components/metrics/occurrences.md)指标填充报表。
1. Google Analytics 中的表通常包含 7-8 个指标。找到“弹出率”指标（绿色），并将其拖动到“发生次数”指标标题旁边。如果将“弹出率”指标拖动到“发生次数”旁边，则这两个指标会并排显示。
1. 通过将指标拖动到现有指标标题旁边，可以并排放置多个指标。有关如何获取 Google Analytics 中常用指标的信息，请参阅[常用指标](common-metrics.md)。

   ![新建指标](/help/technotes/ga-to-aa/assets/new_metric.png)

## 以工作区中的预建报表模板开始

通过访问项目模板创建“内容使用情况”模板（与 Google Analytics 中的“所有页面”报表类似）。

1. 单击“新建项目”按钮。
1. 找到并双击“所有模板”下列出的“内容使用情况 (Web)”图标。
1. 浏览已预建的每个可视化：“登入页面流量”、“热门页面表”、“退出页面流量”、“登入网站区域流量”和“排名最前的网站区域表”。

   ![模板选择](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## 试用该工具

由于 Analysis Workspace 是一款报表工具，因此不会对数据收集产生任何影响。您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。将不同的维度和指标组合拖动到工作区项目中，可查看相应的效果。

如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。此外，您还可以通过单击左上角菜单中的&#x200B;*[!UICONTROL 项目] > [!UICONTROL 新建]*&#x200B;来重头开始创建。

Adobe 在 Analysis Workspace 的右键单击上下文菜单中提供了许多功能。大多数可视化和组件都可以通过右键单击来获取更详细的分析和交互。您可以在工作区中右键单击组件以查看可用选项。

## 了解要使用的维度和指标

如果您熟悉 Analysis Workspace，并且希望重新创建通常在 Google Analytics 中查看的特定报表，请在相应的页面上找到该报表：

* [实时报表](realtime-reports.md)
* [受众报表](audience-reports.md)
* [客户获取报表](acquisition-reports.md)
* [行为报表](behavior-reports.md)
* [转化报表](conversions-reports.md)
