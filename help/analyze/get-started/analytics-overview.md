---
description: 有关Adobe Analytics的一般概述信息
title: Adobe Analytics概述
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: 1c6cc23c9cb6b4b007d2f296ea23e697cc135bd4
workflow-type: tm+mt
source-wordcount: '3101'
ht-degree: 32%

---

# Adobe Analytics概述

Adobe Analytics使组织能够收集数据，并从任何数字客户互动中获得切实可行的见解。 通过深入分析、多用途报表和预测智能，组织可以获得为其客户构建更佳体验所需的深刻基础。

## 主要优点

以下是Adobe Analytics帮助企业获得关键见解以更好地为其客户服务的一些关键方式。

有关Adobe Analytics所提供优势的其他详细信息，请参阅 [Adobe Analytics产品页面](https://business.adobe.com/products/analytics/adobe-analytics.html).

### 网站分析

Adobe Analytics提供了以下复杂的分段和预测工具来分析网站流量：

* [Analysis Workspace中的Ad hoc analysis](/help/analyze/analysis-workspace/home.md)

* [流量分析](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [高级分段](/https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### 营销分析

Adobe Analytics可帮助企业了解客户在何处与其品牌互动，客户更喜欢哪些渠道，以及哪些体验与他们产生了共鸣。

Adobe Analytics中的以下主要功能提供了这些营销功能：

* 多渠道数据收集

* [离线数据集成](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Analysis Workspace中的Ad hoc analysis](/help/analyze/analysis-workspace/home.md)

### 归因

通过归因，组织可以查看整个客户历程中的不同交互如何影响转化。 除了提供更传统的归因选项（例如线性或首次接触模型）之外，Adobe Analytics中的归因还使用机器学习和高级统计模型来了解每次接触产生的精确影响。

有关更多信息，请参阅 [归因模型和回顾时间范围](/help/analyze/analysis-workspace/attribution/models.md).


### 预测分析

预测分析使用机器学习和高级统计建模来分析客户数据、查找模式并预测未来行为，例如流失或转化可能性。 它使数据分析师能够利用原本可能被浪费的巨大数据集。

Adobe Analytics中的以下主要功能提供了这些预测功能：

* [异常检测](#anomaly-detection)

* [贡献分析](#contribution-analysis)

* [智能警报](#intelligent-alerts)

## 使用Adobe Analytics的先决条件

在使用Adobe Analytics之前，您必须拥有：

* 有效的Adobe Analytics许可证

  Adobe Analytics需要站点许可证。 有关更多信息，请与您的Adobe客户代表联系。 <!--is this phrased correctly? Is this important? -->

* 支持的浏览器

  每个访问Adobe Analytics的用户必须使用受支持的浏览器。 欲了解更多信息，请参见 [Adobe Analytics系统要求](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## 了解Analytics界面

Adobe Analytics界面包含以下主要区域：

### “工作区”选项卡

此 [!UICONTROL 工作区] 选项卡显示Analysis Workspace项目的列表。

1. 在Adobe Analytics中，选择 [!UICONTROL **工作区**] 选项卡。

   ![“工作区”选项卡](assets/landing-all2.png)

欲知关于特色与功能的详情，请参阅 [!UICONTROL 工作区] 选项卡，请参见 [Adobe Analytics登录页面](/help/analyze/landing.md).

### “报告”选项卡

Adobe 打算停用 Reports &amp; Analytics 及其随附的报告和功能，从 2023 年 12 月 31 日起生效。

请改用 [!UICONTROL **报表**] 左侧边栏中的区域 [!UICONTROL **工作区**] 选项卡。 有关更多信息，请参阅 *在报告选项卡中导航* 在 [Adobe Analytics登录页面](/help/analyze/landing.md).

### “组件”选项卡

此 [!UICONTROL 组件] 选项卡包含可帮助您优化和增强数据分析功能的功能。

1. 在Adobe Analytics中，选择 [!UICONTROL **组件**] 选项卡，然后选择 [!UICONTROL **所有组件**].

   ![“工作区”选项卡](assets/components-tab.png)

2. 选择以下任何产品功能进行配置：


   | 产品功能 | 函数 | 更多信息 |
   |---------|----------|----------|
   | 区段 | Adobe Analytics 允许您使用各种 Analytics 功能、Adobe Experience Cloud、Adobe Target 和其他集成的 Adobe 产品生成、管理和共享强大而集中的受众区段并将它们应用到您的报表中。 | [Analytics 分段](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=zh-Hans) |
   | 计算指标 | 计算量度和高级计算（或派生）量度是指您可以从现有量度创建的自定义量度。  通过使用这些工具，营销人员、产品经理和分析人员不必更改Analytics实施，即可提出有关数据的问题。 | [计算量度和高级计算（派生）量度](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=en) |
   | 日期范围 | Analysis Workspace包含一系列用户在构建分析时可以使用的默认日期范围。 此外，您还可以创建自定义日期范围，并向Analysis Workspace中的用户提供。 | [创建自定义日期范围](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=zh-Hans) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | 虚拟报表包 |  |  |
   | 警报 | 智能警报允许对警报进行更多粒度控制，并且还将异常检测与警报系统集成在一起。 | [智能警报](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | 目标 | 利用目标可以评测网站的绩效，跟踪目标进度。创建目标时，选择要测量的属性量度或 eVar，或根据所选量度选择测量整个网站。 <p>目标是Reports &amp; Analytics的一部分。 详细了解 Reports &amp; Analytics [生命周期结束公告](https://express.adobe.com/page/6WnF8JK6IRDhf/)。</p> | [目标](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | 日程表事件 | 对于特定时段的趋势报表，日历事件允许您以图形方式显示活动并查看促销活动或其他活动是否影响了您的网站流量、收入或任何其他指标。 | [日历事件](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | 批注 | 工作区批注使您能够有效地将上下文数据的细微差别和见解传达给您的组织。它们可让您将日历事件与特定维度和量度关联起来。 | [管理批注](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | 分类集 | 分类集提供单个界面以管理分类和规则。 <p>分类是在生成报表时对 Analytics 变量数据进行分类，然后以不同的方式显示数据的方法。您可以在变量值与与该值相关的元数据之间建立关系。 分类可用于大多数自定义维度，例如跟踪代码、prop和eVar。</p> | [分类集概述](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=zh-Hans) |
   | 位置 | 要从云目标导入Adobe Analytics分类数据，您首先需要添加和配置希望收集分类数据的位置。 您可以创建、编辑或删除位置。 | [位置管理器](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | 计划项目 | 在管理计划项目时，您可以编辑和删除重复的项目计划；在搜索栏中搜索计划或使用左边栏中的筛选选项搜索计划；并按标记、批准的计划、所有者等内容进行筛选。 | [计划项目](/help/components/scheduled-projects-manager.md) |
   | 书签 | 书签可让您访问最常用的报表。创建的书签会添加到 Experience Cloud 中，并可在 Data Connectors 等集成功能中使用。 <p>书签是Reports &amp; Analytics的一部分。 详细了解 Reports &amp; Analytics [生命周期结束公告](https://express.adobe.com/page/6WnF8JK6IRDhf/)。 | [书签管理器](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | 仪表板 | 创建功能板是为了可视化量度并提供包含数据的交互式分析功能。 通过单击仪表板中的项目，您可以快速轻松地划分数据以从分析中派生信息。 <p>功能板是Data Workbench的一部分。 阅读有关Data Workbench的更多信息 [生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [功能板管理器](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | 计划报表 | 管理员级别的用户可以在整个组织中查看和管理计划报表。 | [计划报表队列](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | 报表设置 | 这些设置是指旧版Adobe Analytics产品，其中不包括Analysis Workspace及其相关组件。 要调整Analysis Workspace设置，请转到组件>首选项。 |  |
   | 偏好设置 | 为您创建的所有新项目或面板管理Analysis Workspace的设置及其相关的组件。 现有项目和面板不受影响。 | [首选项](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### “工具”选项卡

“工具”选项卡……

1. 在Adobe Analytics中，选择 [!UICONTROL **工具**] 选项卡，然后选择 [!UICONTROL **所有工具**].

   ![“工作区”选项卡](assets/tools-tab.png)

2. 选择以下任何产品功能进行配置：

   | 产品功能 | 函数 | 更多信息 |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse 指的是用于存储和自定义报表的 Analytics 数据副本，您可以通过筛选数据来运行这些数据。  <p>请求管理器允许您查看和复制请求，并重新安排请求的优先级。</p> | [管理 Data Warehouse 请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Map旨在使用可视化叠加图为链接活动排名，并提供实时分析功能板，以监控受众在您网页上的参与情况。 通过它可设置不同的视图，以直观地标识客户活动的增速、量化营销举措，并根据受众的需求和行为采取相应的措施。 | [Activity Map 概述](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=zh-Hans) |
   | Recommendations Classic |  |  |
   | Search&amp;Promote |  |  |
   | Mobile Services |  |  |
   | Analytics功能板（移动应用程序） |  |  |
   | Report Builder |  |  |

   {style="table-layout:auto"}

### “管理员”选项卡

“管理员”选项卡……

1. 在Adobe Analytics中，选择 [!UICONTROL **管理员**] 选项卡，然后选择 [!UICONTROL **所有管理员**].

   ![“工作区”选项卡](assets/admin-tab.png)

## 管理员、分析人员和最终用户快速入门

典型组织中有3种Adobe Analytics用户类型：管理员、分析人员和最终用户。

管理员实施和配置Adobe Analytics；分析师使用Analysis Workspace设置项目并创建分析，最终用户通过创建自己的分析或与分析师合作创建分析来获取关于其客户的可操作性见解。

展开以下部分，了解每位用户如何开始使用Adobe Analytics。

### 管理员入门

Analytics管理员负责选择最适合其组织的实施方法。

实施Adobe Analytics后，管理员需要执行各种配置任务，以确保分析人员和最终用户能够从Adobe Analytics中获取全部价值。

#### 确定应收集的数据类型

通过Adobe Analytics，您可以从多种渠道类型中收集数据，并将这些数据整合在一起，以提供有意义的实时客户洞察。

以下是一些受支持的收集数据的渠道：

* 手机

* 物联网

* TV

* 语音助理

* 联网汽车

* 更多（定期添加新的受支持渠道）

此 [实现方法](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hans) 您选择的选项决定了可以收集的数据类型。

#### 实施 Adobe Analytics

在您的网站或移动应用程序上实施Adobe Analytics时，可以使用各种实施方法。

有关每种可用方法的信息，请参见 [实施Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hans).

| | 实施方法 |
|---------|---------|
| **网站** | <ul><li>Web SDK扩展（推荐）</li><li>Web SDK</li><li>Analytics 扩展</li><li>旧版JavaScript</li></ul> |
| **移动设备应用程序** | <ul><li>Mobile SDK扩展（推荐）</li><li>Analytics 扩展</li></ul> |

{style="table-layout:auto"}

#### 配置Adobe Analytics

在将Adobe Analytics提供给组织中的用户之前，Analytics管理员应该完成以下任务：

| 任务 | 预期用途 | 更多信息 |
|---------|----------|---------|
| 定义管理员角色 | Adobe Analytics支持各种类型的管理员 | [Adobe Analytics 中的管理员角色](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| 定义权限 | Analytics管理员需要在Admin Console中为Adobe Analytics、报表包工具和Analytics工具分配产品配置文件。 | [Admin Console 中的 Analytics 权限](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=zh-Hans) |
| 设置报表包并定义公司的设置 | 报表包是Adobe Analytics用于生成报表的数据孤岛。<p>管理员还可以设置 [虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hans) 以进一步细分数据。</p> | <ul><li>[创建报表包](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[公司设置概述](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| 导入数据 | Adobe Analytics数据源允许您导入其他在线或离线数据以便进行报告。 | [数据源概述](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| 使用“分类”功能对数据进行分类 | 通过分类，您可以对数据分类，以更好地利用变量，从而可以将更多内容包含到单个变量中。 | |
| 管理组件 | 使用每个组件类型的数据字典和管理区域来定义Analytics实施中可用的组件，以及组织中批准的组件。<p>这应该是一项持续的活动，可确保您的组织内有效使用组件。 </p> | <ul><li>[数据词典概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=zh-Hans)</li><li>[计算量度管理器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[管理区段](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=zh-Hans)</li><li>[创建自定义日期范围](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=zh-Hans)</li></ul> |
| 异常检测和贡献分析 | | |
| 高级分段 | | |
| 将受众发布到Audience Manager | | |
| 归因 | | |
| 报表活动管理器 | | |
| 集成 | 您可以在Adobe Analytics中显示来自其他应用程序的信息。 <p>以下是一些常见的集成：</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=en">媒体分析</a></li> | |

{style="table-layout:auto"}

### 分析人员快速入门

尽管组织内的任何人可以使用Adobe Analytics获得关于网站和应用程序中客户行为的可操作见解，但Adobe Analytics的设计考虑到了数据分析师。

为了充分利用Adobe Analytics和Analysis Workspace的强大功能，分析人员应该熟悉以下主要任务和功能。

| 功能 | 预期用途 | 更多信息 |
|---------|----------|---------|
| 在Analysis Workspace中构建和共享项目 | Analysis Workspace 是一款通过浏览器即可使用的灵活工具，可让您快速构建和共享分析。您可以使用拖放界面进行分析、添加可视化图表以便直观地呈现数据、梳理数据集、与组织中的任何人共享项目并设置共享频率与时间。<p>数据分析师通常负责在Analysis Workspace中为组织内的用户创建项目。</p><p>创建项目后，分析人员会将这些项目与 [最终用户](#end-users)（非分析人员）来解释这些数据，并且帮助他们了解如何解读这些数据。</p> | <ul><li>[创建项目](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| 归因 | 分析人员可通过在Analysis Workspace中使用各种归因模型和回顾时间范围，自定义维度项目获得成功事件点数的方式。<p>线性归因模型将相同的点数分给促成转化的每个接触点，而首次接触将完全点数分给首次接触点。 还有许多其他归因模型可用，包括算法模型，它使用统计技术动态确定最佳点数分配。 </p> | [归因模型和回顾时间范围](/help/analyze/analysis-workspace/attribution/models.md) |
| 异常检测 | Analysis Workspace中的统计建模通过分析量度并确定值的下限、上限和预期范围，自动查找数据中的意外趋势。 如果发生意外的尖峰或低谷，系统会在报表中进行警报。 | [异常检测概述](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| 贡献分析 | 使用Analysis Workspace发现数据中的隐藏模式可解释统计异常，并识别不同受众区段间意外客户操作、出界值以及量度突升或突降背后的关联。 | [贡献分析概述](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| 智能警报 | 根据数据异常和在一个警报中捕获了多个量度的“栈叠”警报创建和管理警报。 | [智能警报概述](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| 数据导出 | Data Warehouse和数据馈送允许您将数据导出到各种云目标，如Google Cloud Platform、Azure RBAC、Azure SAS和Amazon S3。 | [Analytics 导出指南](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=zh-Hans) |
| Activity Map | Activity Map 是一款 Adobe Analytics 应用程序，专门用于通过可视化叠加图为链接活动排名，并且可以提供实时分析功能板，以监控受众在您网页上的参与度。<p>Activity Map 允许您设置不同的视图，以此来直观地标识客户活动的增速、量化营销举措，并根据受众的需求和行为采取相应的措施。</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=zh-Hans) |
| Report Builder | Report Builder 是 Microsoft Excel 的加载项。通过 Report Builder，您可从插入 Excel 工作表的 Adobe Analytics 数据构建自定义的请求。请求可动态引用工作表中的单元格，并且您可更新和自定义 Report Builder 展示数据的方式。 | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### 最终用户入门

不是专业分析人员的最终用户既可以与其组织中的分析人员合作，充分利用Adobe Analytics和Analysis Workspace的功能，也可以了解Analysis Workspace的基础知识，以便开始获得关于其客户的可操作见解。

#### 与分析人员合作

通常，组织内希望详细了解客户在各种网站上的行为的用户不是专业的分析师。

理想情况下，这些用户应该与 [分析员](#analysts) 在组织内执行以下操作：

1. 通过向分析人员说明他们希望了解的客户信息，定义分析要求。

1. 审查分析以确保其达到目标。

1. 讨论从分析中获得的数据。

1. 随时间根据需要修改分析。

#### 在Analysis Workspace中创建分析

您无需成为数据分析师，即可从Adobe Analytics中获得切实可行的见解。

某些用户可能会发现与数据分析师合作在Analysis Workspace中设置项目并解释如何解释数据很有帮助，如中所述 [与分析人员合作](#work-with-analysts)；其他用户可能乐于自行构建项目并解释数据。

利用 Analysis Workspace，可以快速生成分析以收集见解，然后与其他人共享这些见解。可以使用拖放浏览器界面进行分析、添加可视化图表以便直观地呈现数据、梳理数据集以及与您选定的任何人员共享和安排项目。

有关如何在Analysis Workspace中创建分析的信息，请参阅 [Analysis Workspace概述](/help/analyze/analysis-workspace/home.md).

### 开发人员入门

[使用 Analytics API，您可以直接调用 Adobe 的服务器来执行您可在用户界面中执行的几乎任何操作。](https://developer.adobe.com/analytics-apis/docs/2.0/)

您可以创建报告来进行探索、获取洞察或回答有关数据的重要问题。您还可以管理 Adobe Analytics 的组件，例如创建区段或计算量度。

## 视频概述

要了解Adobe Analytics的基础知识，请查看此 *Adobe Analytics简介 — Skill Builder网络研讨会* 视频。 该视频向您介绍了有关如何捕获数据、如何将数据发送到 Adobe Analytics 以及在 Adobe Analytics 中可以使用哪些可视化功能的基础知识。此视频为您构建、部署、收集和解读数据奠定基础，从而使您能够根据收集的数据提供可操作见解和推荐。

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

有关使用哪种工具的问题，请参阅[我应该使用哪种 Adobe Analytics 工具？](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html)

## 进一步了解Customer Journey Analytics

Customer Journey Analytics 是 Adobe 推出的新一代 Analytics 解决方案，可让您运用 Analysis Workspace 的强大功能处理来自 Adobe Experience Platform 的数据。它可以划分、筛选、查询和可视化数年积累的有价值的数据，并结合 Platform 的功能来保存各种数据架构和类型。

与Adobe Analytics相比，Customer Journey Analytics具有以下一些优势：

* **无限量的变量和事件**：eVar、prop 和事件的概念已不复存在。数据主要侧重于维度和量度。数据集可以有无限数量的唯一维度和量度。

* **无限唯一值**：Adobe Experience Platform 不受任何特有限制的约束。

* **更改历史数据**：使用 Adobe Experience Platform，可以删除或更正数据。

* **跨报告包数据**：可以在 Platform 中组合来自多个数据集的现有实施。

有关更多信息，请参阅 [Customer Journey Analytics概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans).

