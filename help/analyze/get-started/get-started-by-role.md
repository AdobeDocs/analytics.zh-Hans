---
description: 有关 Adobe Analytics 的一般概述信息，包括有关 Analytics 界面的信息以及针对管理员、分析师、用户和开发人员的快速入门信息。
title: 管理员、分析师、最终用户和开发人员快速入门
feature: Analytics Basics
exl-id: 11800de5-224a-4bd2-8cb1-a6318925db71
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 99%

---

# 管理员、分析师、最终用户和开发人员快速入门

典型组织中有 4 种类型的 Adobe Analytics 用户：

* **管理员：**&#x200B;实施和配置 Adobe Analytics。

* **分析师：**&#x200B;使用 Analysis Workspace 设置项目和创建分析

* **最终用户：**&#x200B;通过创建自己的分析或与分析师合作创建分析，获得有关其客户的可操作洞察

* **开发人员：**&#x200B;使用 Adobe Analytics 2.0 API 直接调用 Adobe 的服务器以执行几乎任何可在用户界面中执行的操作，如创建报告以探索、获得洞察或回答有关数据的重要问题。

以下信息概述了每个用户如何开始使用 Adobe Analytics。

## 管理员快速入门

Analytics 管理员负责选择最适合其组织的实施方法。

实施 Adobe Analytics 后，管理员需要执行各种配置任务，以确保分析师和最终用户从 Adobe Analytics 中获得全部价值。管理员还应定期监控其 Analytics 环境以确保系统高效运行。

### 确定应收集的数据类型

Adobe Analytics 可让您从多种渠道类型收集数据并将其整合在一起，以提供有意义的实时客户洞察。

以下是一些可收集数据的受支持渠道：

* 手机

* 物联网

* TV

* 语音助手

* 联网汽车

* 还有更多（定期添加新支持的频道）

[实施方法](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hans)，您的选择决定了可以收集的数据类型。

### 实施 Adobe Analytics

在您的网站或移动应用程序上实施 Adobe Analytics 时，可以使用多种实施方法。

关于每种可用方法的信息，请参阅[实施 Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hans)。

| | 实施方法 |
|---------|---------|
| **网站** | <ul><li>Web SDK 扩展（推荐）</li><li>Web SDK</li><li>Analytics 扩展</li><li>旧版 JavaScript</li></ul> |
| **移动设备应用程序** | <ul><li>移动 SDK 扩展（推荐）</li><li>Analytics 扩展</li></ul> |

{style="table-layout:auto"}

### 配置 Adobe Analytics

Analytics 管理员应先完成以下任务，然后再向组织中的用户提供 Adobe Analytics：

| 任务 | 有可能的使用 | 更多信息 |
|---------|----------|---------|
| 定义管理员角色 | Adobe Analytics 支持各种类型的管理员 | [Adobe Analytics 中的管理员角色](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=zh-Hans) |
| 定义权限 | Analytics 管理员需要在 Adobe Analytics、报告包工具和分析工具的 Admin Console 中分配产品轮廓。 | [Admin Console 中的 Analytics 权限](/help/admin/admin-console/permissions/analytics-tools.md) |
| 设置报告包并为您的公司定义设置 | 报告包是一种数据存储库，Adobe Analytics 使用报告包生成报表。<p>管理员还可以设置[虚拟报告包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hans)进一步细分数据。</p> | <ul><li>[创建报告包](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=zh-Hans)</li><li>[公司设置概述](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=zh-Hans)</li></ul> |
| 导入数据 | Adobe Analytics 数据源允许您导入其他在线或离线数据以便进行报告。 | [数据源概述](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=zh-Hans) |
| 使用“分类”对数据进行分类 | “分类”允许您对数据进行分类，以更好地利用变量，从而将更多内容包含到单个变量中。 | [分类概述](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-overview.html?lang=zh-Hans) |
| 管理组件 | 使用“数据字典”和每个组件类型的管理区域来定义哪些组件在您的 Analytics 实施中可用，以及哪些组件已批准供您的组织使用。<p>这应该是一项持续的活动，以确保组件在您的组织中得到有效使用。 </p> | <ul><li>[数据词典概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=zh-Hans)</li><li>[计算量度管理器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=zh-Hans)</li><li>[管理区段](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=zh-Hans)</li><li>[创建自定义日期范围](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=zh-Hans)</li></ul> |
| 异常检测 | “异常检测”提供了一种统计方法来确定给定的量度相对于以前的数据发生了什么变化。 | [异常检测概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=zh-Hans) |
| 贡献分析 | “贡献分析”可揭示数据中隐藏的模式以解释统计数据的异常，并可以跨各受众区段，确定意外客户操作、出界值以及选定量度的突增或突减背后存在的关联。 | [贡献分析概述](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| Analytics 分段 | 可让您使用各种 Analytics 功能、Adobe Experience Cloud、Adobe Target 和其他集成的 Adobe 产品生成、管理和共享强大而集中的受众区段并将它们应用到您的报表中。 | [Analytics 分段](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=zh-Hans) |
| 将受众发布到 Audience Manager | Adobe Audience Manager 是一个强大的数据管理平台，它帮助您从第一方、第二方（合作伙伴）和第三方的数据集成构建独特的受众轮廓。 | [Audience Analytics 概述](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=zh-Hans) |
| 集成 | 您可以在 Adobe Analytics 中显示来自其他应用程序的信息。 <p>以下是一些常见的集成：</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=zh-Hans">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hans">流媒体服务</a></li> | [Analytics 集成](https://experienceleague.adobe.com/docs/analytics/integration/home.html?lang=zh-Hans) |

{style="table-layout:auto"}

### 监控 Adobe Analytics

提供了多种功能来帮助您监控 Adobe Analytics 环境。

Analytics 管理员应了解以下可用于帮助监控 Analytics 环境的重要方面的功能：

| 任务 | 有可能的使用 | 更多信息 |
|---------|----------|---------|
| 报告活动管理器 | 通过报告活动管理器，可查看组织中每个报告包的报告容量。它可让您详细了解报告消耗，并帮助您轻松地诊断和修复在报告高峰期出现的容量问题。 | [报告活动管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=zh-Hans) |
| 服务器调用使用情况 | 服务器调用又称为“点击”或“图像请求”，它是一种将数据发送到 Adobe 服务器进行处理的实例。提供了“服务器调用使用情况”功能板，来跟踪服务器调用使用情况数据，并将其与合同中的使用限制进行比较。可以设置警报以防止超额情况。 | [服务器调用使用情况概述](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=zh-Hans) |
| 日志文件 | 日志文件有助于您了解用户登录的时间、用户使用情况、访问情况、报告包，以及管理员执行的更改。 | [日志](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=zh-Hans) |

{style="table-layout:auto"}

## Analysts 快速入门

虽然组织中的任何人都可以使用 Adobe Analytics 来获取有关跨网站和应用程序的客户行为的可操作洞察，但 Adobe Analytics 在设计时就考虑到了数据分析师的需求。

以下是分析师应熟悉的关键任务和功能，以便充分利用 Adobe Analytics 和 Analysis Workspace 的强大功能。

| 功能 | 有可能的使用 | 更多信息 |
|---------|----------|---------|
| 在 Analysis Workspace 中构建和共享项目 | Analysis Workspace 是一款通过浏览器即可使用的灵活工具，可让您快速构建和共享分析。您可以使用拖放界面进行分析、添加可视化图表以便直观地呈现数据、梳理数据集、与组织中的任何人共享项目并设置共享频率与时间。<p>数据分析师通常负责在 Analysis Workspace 中为其组织内的用户创建项目。</p><p>创建项目后，分析师将这些项目共享给[终端用户](#end-users)（非分析师），在其组织中请求数据并帮助他们了解如何解释数据。</p> | <ul><li>[创建项目](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| 归因 | 分析师可以通过在 Analysis Workspace 中采用各种归因模型和回溯 Windows，自定义维度项目如何获得成功事件的功劳。<p>线性归因模型对导致转化的每个接触点给予同等的功劳，而首次接触则对第一个接触点给予全部功劳。还有许多其他归因模型可用，包括算法模型，该模型使用统计技术来动态确定信用的最佳分配。 </p> | [归因模型和回顾时间范围](/help/analyze/analysis-workspace/attribution/models.md) |
| 异常检测 | Analysis Workspace 中的统计建模通过分析指标并确定值的下限、上限和预期范围，自动发现数据中的意外趋势。如果发生意外的尖峰或低谷，系统会在报表中进行警报。 | [异常检测概述](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| 贡献分析 | 使用 Analysis Workspace 发现数据中隐藏的模式，以解释统计异常并识别意外客户行为、越界值以及跨受众区段量度的突增或突减背后存在的关联。 | [异常检测概述](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)中的[贡献分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| 警报 | 基于数据异常和在单个警报中捕获多个量度的“堆叠”警报创建和管理警报。 | [警报概述](/help/components/c-alerts/intellligent-alerts.md) |
| 数据导出 | Data Warehouse 和“数据馈送”允许您将数据导出到各种云目的地，例如 Google 云平台、Azure RBAC、Azure SAS 和 Amazon S3。 | [Analytics 导出指南](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=zh-Hans) |
| Activity Map | Activity Map 是一款 Adobe Analytics 应用程序，专门用于通过可视化叠加图为链接活动排名，并且可以提供实时分析功能板，以监控受众在您网页上的参与度。<p>Activity Map 让您可以设置不同的视图，以此来直观地标识客户活动的增速、量化营销方案，并根据受众的需求和行为采取相应的措施。</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=zh-Hans) |
| Report Builder | Report Builder 是 Microsoft Excel 的加载项。通过 Report Builder，您可从插入 Excel 工作表的 Adobe Analytics 数据构建自定义的请求。请求可动态引用工作表中的单元格，并且您可更新和自定义 Report Builder 展示数据的方式。 | [Report Builder](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/rb-overview) |

<!-- * Realtime reporting? -->

## 最终用户快速入门

非专业分析师的最终用户可以与组织中的分析师合作，充分利用 Adobe Analytics 和 Analysis Workspace 的全部功能，也可以学习 Analysis Workspace 的基础知识，以便开始获得有关客户的可操作洞察。

### 与分析师合作

通常，组织中有兴趣详细了解各个站点上的客户行为的用户不是专业分析师。

理想情况下，这些用户应该与[分析师](#analysts)在组织内：

1. 通过向分析师解释他们希望了解客户的哪些信息来定义分析要求。

1. 审查分析以确保它们达到目标。

1. 讨论从分析中获得的数据。

1. 随着时间的推移根据需要修改分析。

### 在 Analysis Workspace 中创建分析

您无需成为数据分析师即可从 Adobe Analytics 获得可操作洞察。

如[与分析师合作](#work-with-analysts)中所述，有些用户可能会发现与数据分析师合作在 Analysis Workspace 中设置项目并解释如何解释数据很有帮助；其他用户可能会轻松构建项目并自行解释数据。

利用 Analysis Workspace，可以快速生成分析以收集见解，然后与其他人共享这些见解。可以使用拖放浏览器界面进行分析、添加可视化图表以便直观地呈现数据、梳理数据集以及与您选定的任何人员共享和安排项目。

有关如何在 Analysis Workspace 中创建分析的信息，请参阅 [Analysis Workspace 概述](/help/analyze/analysis-workspace/home.md)。

## 开发人员快速入门

使用 [Analytics API](https://developer.adobe.com/analytics-apis/docs/2.0/)，您可以直接调用 Adobe 的服务器来执行您可在用户界面中执行的几乎任何操作。

您可以创建报告来进行探索、获取洞察或回答有关数据的重要问题。您还可以管理 Adobe Analytics 的组件，例如创建区段或计算量度。

>[!MORELIKETHIS]
>
>[创建解决方案设计文档](/help/implement/prepare/solution-design.md)
>
