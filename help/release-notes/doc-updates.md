---
title: Adobe Analytics 技术文档更新
description: 对 Adobe Analytics 文档集的重要更新。
short-title: Analytics documentation updates
feature: Release Notes
exl-id: fe8e3c4c-6782-46f7-8e28-4f8f54807788
mini-toc-levels: 3
source-git-commit: df9c6d59ef5f5c43d0e1ef822bd23bc0e09ff20e
workflow-type: tm+mt
source-wordcount: '5047'
ht-degree: 98%

---

# Adobe Analytics 技术文档更新

自 2019 年 1 月以来的 Adobe Analytics 文档集内容更新。

* 有关 [!UICONTROL Customer Journey Analytics] 的信息，请转到[此处](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=zh-Hans)。
* 有关 Adobe Media Analytics 的信息，请参阅[在 Analytics 中测量音频和视频](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hans)。

## 有关主要文档更新的详细信息

### 2024 {#24}

| 功能 | 描述 |
| --- | --- |
| **2024 年 1 月** | |
| 组件迁移适用于单个IMS组织 | 阐明 [组件迁移](/help/admin/admin/component-migration/component-migration.md) 不支持跨IMS组织迁移。 |
| 阐明某些信息仅供管理员使用 | 添加了信息来声明“上次使用”和“用于”列，详见 [计算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) 和 [区段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md) 仅适用于系统管理员。 |
| 媒体平均受众访问分钟数文档更新 | 更新了[媒体平均受众访问分钟数面板](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)中的信息，以提高清晰度。<p>其中的改进包括：</p> <ul><li>改进了信息的条理</li><li>添加了相应步骤以指示基于任务的信息</li></ul> |

### 2023 {#23}

| 功能 | 描述 |
| --- | --- |
| **2023 年 12 月** | |
| 改进了机器人规则文档 | 更新了[了解和配置机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)中的信息以使其更明确。<p>其中的改进包括：</p> <ul><li>更新了文章标题以使其更具描述性</li><li>改进了信息的条理</li><li>添加了相应步骤以指示基于任务的信息</li><li>关于在上传机器人规则时对 CSV 文件的要求添加了更多详细信息</li></ul> |
| 新报告部分 | 添加了新的报告部分，其中包括有关[使用预建报告](/help/analyze/analysis-workspace/reports/use-reports.md)以及[创建和管理公司报告](/help/analyze/analysis-workspace/reports/create-company-reports.md)的信息。 |
| 异常检测和贡献分析文档的更新 | 异常检测和贡献分析的文档以前位于有关 Virtual Analyst 的部分中。进行了以下更改： <ul><li>术语 Virtual Analyst 已从文档中删除。</li><li>关于[异常检测](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)的部分已直接移至 Analysis Workspace 部分下方。</li><li>贡献分析文档已合并到异常检测文档中。</li></ul> |
| “Attribution IQ”改为“Attribution” | 将整个文档中“Attribution IQ”的所有实例更改为“[Attribution](/help/analyze/analysis-workspace/attribution/overview.md)”。 |
| **2023 年 11 月** | |
| 更新了 Activity Map 激活/启用主题 | 添加了 [Web SDK](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/getting-started/activitymap-enable.html?lang=zh-Hans)（手动和通过 Adobe Experience Platform 标记扩展）内容。 |
| **2023 年 10 月** | |
| 将日志信息添加到报告活动管理器 | 添加了一条信息，该信息表示在报告活动管理器中对于[报告活动的任何取消和后续限制](/help/admin/admin/reporting-activity-manager/reporting-activity-cancel-requests.md)都被记录在[日志](/help/admin/admin/logs.md)中。 |
| 更新了 Data Warehouse 对组件的支持情况 | 增加了 Data Warehouse 的一些组件的可用性并删除了其他组件的可用性。这些更改反映在 [Data Warehouse 中的组件支持](/help/export/data-warehouse/component-support.md)中。 <ul><li>增加了对“访问深度”维度的支持（从不支持的维度的列表中删除了“访问深度”）</li><li>删除了对参与率量度的支持（已将参与率量度添加到不支持的量度的列表）</li><li>增加了对以下基于时间的维度的支持：年、季度、月、周、日、小时和分钟（从不支持的维度的列表中删除了这些维度） <p>以前在选择粒度时，Data Warehouse 仅在自由格式表的第一列中支持这些维度。现在始终支持这些维度。</p><p>但是，在使用这些维度时，日期的输出不是标准格式。年份为减去 1900 所得，月份从零开始。</li></ul> |
| **2023 年 9 月** | |
| 更新了“媒体播放耗时”面板的文章结构 | 删除了名为“媒体播放耗时”的文件夹，并将该文件夹的内容合并为一篇文章：[“媒体播放耗时”面板](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)。 <p>此更改与其他面板的文档更一致。</p> |
| 快速入门内容改善 | 增加了信息来概述管理员、分析师、最终用户和开发人员的重要快速入门任务和资源。以下新文章现已可用： <ul><li>[快速入门（按角色）](/help/analyze/get-started/get-started-by-role.md)</li><li>[了解 Analytics 界面](/help/analyze/get-started/analytics-interface.md)<li>[用例](/help/analyze/get-started/use-cases.md)</li></ul> |
| 媒体分析报告文档改进 | 重新整理了流媒体指南的“报告”部分中的一些内容，包括将 API 文档并入其自己的部分中并调整了一些文章的顺序。 <p>已将媒体工作区模板文章重命名为 [Workspace 中的媒体报告](https://experienceleague.adobe.com/docs/media-analytics/using/media-reports/media-workspace-templates.html?lang=zh-Hans)，更好地与产品内命名保持一致。 </p> |
| **2023 年 8 月** | |
| 数据馈送说明 | 更新了[开始日期和结束日期的定义](/help/export/analytics-data-feed/create-feed.md)以说明在处理历史数据的数据馈送时，可将开始日期设置为任何过去收集数据时的日期。 |
| Experience Edge 数据处理 | 添加了有关 Adobe Analytics 如何[处理来自 Experience Edge 的数据](../implement/aep-edge/overview.md)的内容。 |
| “媒体播放耗时”面板 | 更新了[“媒体播放耗时”面板](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)的内容以提高可读性。 |
| 移动了关于管理计划项目的内容 | 在《Analytics 组件指南》中创建了一篇名为[计划项目](/help/components/scheduled-projects-manager.md)的新文章。此内容以前位于《Analytics 工具指南》中的[计划项目](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)一文中。 |
| 比较实施方法 | 更新了比较不同实施方法的文档。[了解详情](../implement/prepare/comparison.md) |
| 阐明为数据馈送配置 SFTP 不需要 Adob&#x200B;e 客户服务 | 在[将 Adobe 数据发送到 SFTP 的外部 FTP 帐户](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)中说明，客户无需联系 Adobe 客户服务，即可为数据馈送配置 SFTP。 <p>还添加了一条注释，即不再建议使用 SFTP，并且客户在配置数据馈送时应使用云目标。</p> |
| 改进了流媒体的文档 | 改进了流媒体文档的以下几点： <ul><li>更新了[一般概述](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hans)以使文档表述更加清晰并包括与 Customer Journey Analytics 相关的信息。</li><li>更新了[实施概述](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html?lang=zh-Hans)以明确地区分 Edge 实施和仅 Analytics 实施。还加入了图表以说明各种实施方法。</li><li>添加了 [Edge 实施](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/edge-recommended/prerequisites-edge.html?lang=zh-Hans)和[仅 Analytics 实施](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/analytics-only/prerequisites-analytics.html?lang=zh-Hans)特有的先决条件。还更新了[一般先决条件](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/prereqs.html?lang=zh-Hans)。</li><li>更新了[获取媒体 SDK、使用标记的扩展和 OTT SDK](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/download-sdks.html?lang=zh-Hans) 文章中的表以加入新的&#x200B;*支持的解决方案*&#x200B;和&#x200B;*实施方法*&#x200B;列。</li><li>简化了文档的[实施](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html?lang=zh-Hans)区域中文章的内容和组织方式。其中包括按 Edge 实施和仅 Analytics 实施为实施分类。</li><li>删除了在[跟踪](https://experienceleague.adobe.com/docs/media-analytics/using/tracking/track-core-overview.html?lang=zh-Hans)下一个用不到的额外层级，并在此部分中添加了重定向到已更改的 URL。</li><ul> |
| **2023 年 7 月** | |
| Adobe Experience Platform Edge Network Server API | 添加了关于何时以及如何使用 [Adobe Experience Platform Edge Network Server API](../implement/aep-edge/server-api/overview.md) 通过 Adobe Analytics 实施数据收集的更全面的文档。例如，在桌面应用程序、物联网设备、机顶盒中通过 Adobe Analytics 实施数据收集。 |
| 全球公司 ID | 已为您登录的 Analytics 公司记录[如何查找全球公司 ID](../admin/admin/company/web-services-admin.md)。Analytics 2.0 API 需要此 ID。 |
| 已更新 FTP 大小限制 | 已将默认 [FTP 数据存储限制](/help/export/ftp-and-sftp/ftp-limits.md)更改为 100 GB。 |
| 新 AppMeasurement 变量 | 变量 `decodeLinkParameters` 可适应一些少见的情况，其中实施在链接跟踪变量中编码多字节字符。[了解详情](../implement/vars/config-vars/decodelinkparameters.md) |
| 配置云帐户存储位置以摄取分类数据 | 您现在可以管理用于分类集自动化的云帐户存储位置。[了解详情](/help/components/locations/configure-import-accounts.md) |
| “数据修复”过滤器增强功能 | 已向“数据修复”添加三项过滤改进。[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) |
| **2023 年 6 月** | |
| 分类集的新增功能 | 已为[分类集](/help/components/classifications/sets/overview.md)添加多项新功能：<ul><li>**合并**：将多个分类集合并为一个统一的分类集。可以像使用其他分类集一样使用统一的分类集，也可以将其用作 Customer Journey Analytics 中的查找数据集。[了解详情](../components/classifications/sets/consolidations/manage.md)</li><li>**规则**：根据分类集中的规则自动对值进行分类。[了解详情](../components/classifications/sets/manage/rules.md)</li><li>**自动化导入**：自动从云存储目标导入分类数据。[了解详情](../components/classifications/sets/manage/schema.md)</li></ul> |
| 计算量度更新 | 已更新与计算量度相关的各种文章，包括更新屏幕截图和过程中的步骤。作出这些更改是为了使文档与当前的 Adobe Analytics 功能保持一致。 |
| 数据馈送导出到安全目标 | 现在可以将数据馈送发送到以下云存储目标：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>不再推荐以前可用的目标（FTP、SFTP、S3 和 Azure Blob）。[了解详情](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hans) |
| Workspace 中的机器人报表 | Analysis Workspace 中现在有机器人报表可用。此功能附带了几项额外功能：<ul><li>一个新维度：[机器人名称](/help/components/dimensions/bot-name.md)</li><li>两个新量度：[机器人页面查看次数](/help/components/metrics/bot-page-views.md)和[机器人发生次数](/help/components/metrics/bot-occurrences.md)。</li><li>一个新的计算量度模板：[机器人页面查看率](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>一个新的 Workspace 报表：机器人报表</li></ul>新维度和量度包含自 2023 年 3 月起开始回填的数据。 |
| **2023 年 5 月** | |
| 深层链接（移动应用程序）文档 | 使用户可发送记分卡的链接，而这些链接将引导用户直接进入应用程序中的记分卡项目。[了解详情](/help/analyze/mobile-app/create-scorecard.md#shareable-link) |
| 关于 Analytics 功能板应用程序（移动应用程序）更新的主屏幕的文档 | 通过新近更新的主屏幕，可在一个合并的记分卡列表中查看您的所有记分卡。[了解详情](/help/analyze/mobile-app/executive.md#use-dashboards) |
| Spectrum 图标 | 已适当地将文档中用户界面图标的屏幕截图替换为引用 [Adobe 的 Spectrum 设计系统](https://spectrum.adobe.com/page/icons/)中的同等图标。 |
| 报告活动管理器 | 更新了此 Beta 文档，尤其是更新了关于[查看个别报表包的报告活动](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html#view-reporting-activity-for-individual-report-suites)的部分。 |
| Analysis Workspace 概述 | 更新了 [Analysis Workspace 概述](/help/analyze/analysis-workspace/home.md)，包括更多的一般概述信息和相关内容的链接。 |
| 创建项目 | 创建了一篇新文章，其中详细解释了如何在 Analysis Workspace 中[创建项目](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)。 |
| 为左边栏中的组件排序 | 添加了有关对左边栏中的组件列表进行排序的信息。请参阅[组件概览](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)中的“搜索、过滤和排序组件列表”部分。 |
| 从自由格式表中删除包含动态维度的行 | 添加了有关如何使用 x 图标快速删除包含动态维度的特定行的信息。请参阅[过滤表和为其排序](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的“从表中快速排除特定行”部分。 |
| 面板中添加可视化效果的按钮 | 添加了有关 Analysis Workspace 中每个面板底部的新按钮的信息，通过该按钮，可快速地添加可视化效果。请参阅[可视化概述](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)中的“将可视化效果添加到面板”部分。 |
| **2023 年 4 月** | |
| 转移用户资源和设置帐户到期 | 添加了关于如何[转移用户资源和设置帐户到期](/help/admin/admin/user-management2/users-assets.md)的信息。 |
| 面向 Adobe Analytics 2.0 API 的 2 个新端点指南 | <ul><li>[Analytics 维度 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[Analytics 量度 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> |
| 项目区段（临时区段和快速区段） | 简化了有关项目区段的文档并删除了重复的信息。创建临时区段的步骤现在与[创建快速区段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)的步骤合并在一起。 |
| 动态查找 | 添加了关于[动态查找](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md)的其他信息。以前对于移动属性仅存在“信息”，而它仅为若干动态查找之一。 |
| **2023 年 3 月** | |
| Web SDK 对 Activity Map 的支持 | 更新了[实施 Adobe Analytics](/help/implement/home.md) 和[启用 Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md)。 |
| 流量变量 (prop) 概述 | 添加了章节和分步过程以阐明和改善文章内容。合并了标题为“启用流量变量报告”一文的内容并删除了这篇文章。请参阅[流量变量 (prop) 概述](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)。 |
| 内部 URL 过滤器 | 添加了章节和分步过程以阐明和改善文章内容。请参阅[内部 URL 过滤器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。 |
| 在移动记分卡中创建数据故事 | [数据故事](/help/analyze/mobile-app/create-scorecard.md#create-data-stories)是围绕中心主题或量度构建的辅助数据点、业务背景和相关量度的集合。 |
| 默认计算量度 | 添加了解释 [Adobe 提供的默认计算量度](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)的内容。 |
| 数据词典 | <p>添加了数据词典的新文档，包括[概述](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)、[查看](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md)、[编辑](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)和[监控](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)数据词典。</p><p>更新了[添加组件描述](/help/analyze/analysis-workspace/components/add-component-descriptions.md)中的信息以解释数据词典功能。</p> |
| 共享项目链接（无需登录） | <p>更新了现有文档以说明如何与无权访问 Analysis Workspace 的人员共享项目的只读链接。</p> <p>更新后的用户文档包括[共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md)和[创建可共享链接](/help/analyze/analysis-workspace/curate-share/shareable-links.md)。</p> <p>已将管理员的选项添加到[偏好设置](/help/analyze/analysis-workspace/user-preferences.md)。</p> |
| **2023 年 2 月** | |
| 实施 | 更新了有关如何[为 Web 和移动设备实施 Adobe Analytics](../implement/home.md) 的内容。 |
| 工作区日程表和日期范围 | 更新内容以描述相对日期范围、公式计算更新和日程表 UI 更改。请参阅[关于相对面板日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)。 |
| 移动记分卡 | 新文档部分描述如何显示和隐藏比较日期范围。请参阅 Customer Journey Analytics 中的[显示比较日期范围](/help/analyze/mobile-app/create-scorecard.md)。 |
| 1.4 API | [Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/) 经过了全面改写，现在发布在 Adobe Developer 上。 |
| 跟踪各实施类型 | 更新了用例[跟踪不同的实施类型](../implement/use-cases/cross-type-implementation.md)以适应 Experience Cloud ID 服务。 |
| **2023 年 1 月** | |
| 排序和过滤表格 | 更新了[对表格进行筛选和排序](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)一文中的内容（包括添加过程和解释可用选项）。本文从“对表格进行分页、筛选和排序”更名而成。 |
| 文件夹 | [文件夹管理](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)的专用页面。 |
| 用户偏好设置 | [偏好设置](/help/analyze/analysis-workspace/user-preferences.md)中现在提供了许多其他用户偏好设置。 |
| 项目的自动保存 | 已更新内容以在[保存项目](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)中包含自动保存功能。 |
| 登陆页面 | 新的[登陆页面更新](/help/analyze/landing.md) |

### 2022 {#22}

| 功能 | 描述 |
| --- | --- |
| **2022 年 11 月** | |
| 同意管理变量 | [同意管理选择加入](/help/components/dimensions/cm-opt-in.md)和[同意管理选择退出](/help/components/dimensions/cm-opt-out.md)的专用页面。 |
| 多货币更新 | 有关[多货币支持](/help/implement/vars/config-vars/currencycode.md)的页面已更新。 |
| **2022 年 10 月** |  |
| Data Workbench | [生命周期终止通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans) |
| 客户端提示 | 新的[概述和常见问题解答 ](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=zh-Hans)。 |
| 关键量度摘要 | 关于[关键量度摘要](/help/analyze/analysis-workspace/visualizations/key-metric.md)可视化的新主题。 |
| 分类集 | 新用户[分类集](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=zh-Hans)体验提供单个界面以管理分类和规则，并更容易看到客户拥有的分类数据。 |
| 移动应用程序：自定义详细信息视图 | 关于[自定义详细视图](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=zh-Hans)的新主题。 |
| VISTA | 新页面解释了 [VISTA 规则](/help/technotes/vista.md)的基本信息。 |
| **2022 年 9 月** | |
| 组合图表 | 有关[组合图表](/help/analyze/analysis-workspace/visualizations/combo-charts.md)可视化的新主题。 |
| 更新的插件 | 更新了 [getvalonce](/help/implement/vars/plugins/getvalonce.md) 实施插件的版本。 |
| 新增配置变量 | 关于 [collectHighEntropyUserAgentHints](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) 的文档 |
| 高熵客户端提示 | 关于 Adobe 如何在 User-Agent 之外使用[客户端提示](/help/technotes/client-hints.md)确定设备信息的新主题。 |
| 处理顺序 | 我们已聚合多个帮助页面以仅提供一个关于[处理顺序](/help/technotes/processing-order.md)的帮助主题。 |
| **2022 年 8 月** | |
| 在用于 Edge Collection 的 XDM 中支持列表变量 | 使客户能够通过 Experience Edge/Web SDK 收集数据，以使用 XDM 指定列表变量内容[了解详情](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/list.html?lang=zh-Hans#list-variables-using-the-web-sdk?lang=zh-Hans) | 2022 年 8 月 18 日 |
| 设置产品字符串变量时在用于 Edge Collection 的 XDM 中使用 SKU 字段 | 使客户能够通过 Experience Edge/Web SDK 收集数据，以使用 SKU 值设置产品变量中的产品字段[了解详情](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=zh-Hans#products-using-the-web-sdk?lang=zh-Hans) |
| **2022 年 6 月** |  |
| 用于 Edge Collection 的 XDM 中的促销变量 | 关于[支持用于 Edge Collection 的 XDM 中促销变量的文档](/help/components/dimensions/evar-merchandising.md) |
| Experience Platform Edge 文档 | 关于通过 [Web SDK](/help/implement/aep-edge/web-sdk/overview.md)、[Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) 和 [Edge API](/help/implement/aep-edge/server-api/overview.md) 实现 Adobe Analytics 的新文章。 |
| 更新的流量可视化文档 | 基于[新 UI](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| 关于在移动记分卡中共享注释的文档 | 您可以[在移动记分卡中显示在工作区中创建的注释](/help/analyze/analysis-workspace/components/annotations/mobile-annotations.md)。 |
| **2022 年 5 月** | |
| 通过 Experience Edge 填充生命周期维度和量度 | Analytics 报告中现在显示通过 Experience Edge 发送的移动生命周期数据。有关哪些 XDM 字段映射到现有移动生命周期报告的详细信息，请参阅 [Analytics 变量映射](/help/implement/aep-edge/variable-mapping.md)。 |
| **2022 年 4 月** | |
| Adobe Analytics 登陆页面更新 | 更新了联合 [Workspace/Reports &amp; Analytics 登录页面](/help/analyze/landing.md)，从而提高可用性和导航便利性。 |
| 关于[!UICONTROL 页面摘要]面板的新主题 | [页面摘要](/help/analyze/analysis-workspace/c-panels/page-summary.md)面板 |
| 关于[!UICONTROL 下一项/上一项]面板的新主题 | [下一维度项/上一维度项](/help/analyze/analysis-workspace/c-panels/next-previous.md)面板 |
| **2022 年 3 月** | |
| 关于支持的 HTTPS 加密算法的新主题 | [对于将密码安全级别设置为“High”的客户支持的 HTTPS 加密算法](/help/technotes/rdc/encryption-algos.md)。 |
| 关于工作区中注释的新文档 | [工作区中注释](/help/analyze/analysis-workspace/components/annotations/overview.md)使您能够有效地将上下文数据的细微差别和见解传达给您的组织。 |
| Adobe Analytics 登陆页面更新 | [更新联合工作区/Reports &amp; Analytics 登录页面，提高可用性和导航的便利性。](/help/analyze/landing.md) |
| [!UICONTROL 下一个项目]或[!UICONTROL 上一个项目]工作区面板 | 此面板允许您浏览所选维度项目之后或之前的项目。 |
| [!UICONTROL 页面摘要]工作区面板 | 此面板为您选择的页面提供深入分析。 |
| 关于暂停旧版计划报告的新主题 | 从 **2022 年 4 月 15 日**&#x200B;起，Adobe 打算暂停所有创建日期超过两年的计划报告 |
| **2022 年 2 月** |
| 移动记分卡项目预览模式 | 该[预览模式](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=zh-Hans#preview?lang=zh-Hans)允许您在保存和共享记分卡之前预览体验。 |
| API 项目端点 | 使用 API 添加、编辑或删除 Analysis Workspace 项目。[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) |
| 暂停旧版计划 Report Builder 任务更新主题 | **从 2022 年 4 月 15 日起**，Adobe 打算[暂停所有在大于两年之前创建的计划 Report Builder 任务](/help/analyze/report-builder/r-arb-scheduled-reports.md)。 |

### 2021 {#21}

| 功能 | 描述 |
| --- | --- |
| **2021 年 10 月** |  |
| 2021 年 10 月 21 日 | 有关 Analysis Workspace 中的[快速区段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=zh-Hans)的新文档 |
| 2021 年 10 月 21 日 | 有关 Analysis Workspace 中的[媒体播放耗时](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=zh-Hans)面板的新文档。 |
| 2021 年 10 月 7 日 | 有关[移动记分卡可视化](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=zh-Hans#apply-visualizations?lang=zh-Hans)的新文档 |
| **2021 年 8 月** |  |
| 2021 年 8 月 18 日 | 修订了顶层结构，合并为一个[登陆页面](https://experienceleague.adobe.com/docs/analytics.html?lang=zh-Hans) |
| 2021 年 8 月 18 日 | 有关 [A4T 和虚拟报告包](/help/components/vrs/vrs-a4t.md)的新主题 |
| 2021 年 8 月 18 日 | 有关[归因最佳实践](/help/analyze/analysis-workspace/attribution/best-practices.md)的新主题 |
| 2021 年 8 月 5 日 | 有关[计算重复实例](https://experienceleague.adobe.com/docs/analytics/components/metrics/count-repeat-instances.html?lang=zh-Hans)的新主题 |
| 2021 年 8 月 5 日 | 更新了有关[模板](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-download-saint-data.html?lang=zh-Hans)、[浏览器导入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=zh-Hans)和[浏览器导出](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-export.html?lang=zh-Hans)的分类文档，以指示对启用新分类架构的报告包不可用的选项。 |
| 2021 年 8 月 2 日 | 更新了多个页面以反映 [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=zh-Hans) 的重新品牌化 |
| **2021 年 7 月** |  |
| 2021 年 7 月 23 日 | 对[促销 eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=zh-Hans) 的全新深入讨论 |
| 2021 年 7 月 15 日 | 新增有关新的 [Adobe Analytics 登陆页面](/help/analyze/landing.md)的文档 |
| **2021 年 6 月** |  |
| 2021 年 6 月 15 日 | 更新了[营销渠道最佳实践](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=zh-Hans) |
| 2021 年 6 月 3 日 | 更新了文档以更好地说明[数据馈送实施](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hans)，请参阅[此处](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=zh-Hans#BucketOwnerFullControl)。 |
| 2021 年 5 月 25 日 | 更新了有关[报告中的 eVar 区分大小写](https://experienceleague.adobe.com/docs/analytics/components/dimensions/evar.html?lang=zh-Hans)的文档。 |
| 2021 年 5 月 13 日 | 更新了 [Data Warehouse API 请求](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/reporting-api/data_warehouse.md)。它们现在支持“Hours”。 |
| **2021 年 3 月** | |
| 2021 年 3 月和 4 月 | 更新了 Adobe Analytics 功能板[执行人指南](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/executive.html?lang=zh-Hans)和[策划人指南](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html?lang=zh-Hans) |
| 2021 年 3 月 25 日 | 有关[!UICONTROL 组件] > [!UICONTROL 用户偏好设置]页面的新文档。它使您能够为用户管理 [!UICONTROL Analysis Workspace] 设置及其相关的组件。[!UICONTROL “用户偏好设置”]适用于所有新的项目和面板。<br>**注意：**&#x200B;以下设置已移至[!UICONTROL “用户偏好设置”]页面：<ul><li>报告设置：千位分隔符（现在称为&#x200B;_“数字格式”_）</li><li>报告设置：CSV 分隔符</li><li>工作区项目：“帮助”>“启用提示”</li><li>工作区项目：空白面板的&#x200B;_“用此面板开始新项目”_&#x200B;选项</li></ul> |
| 2021 年 3 月 25 日 | [!UICONTROL “直方图智能存储桶预测”]帮助高基数量度直方图为您的数据分布自动识别存储桶的合适宽度和数量。对于低基数量度，可视化的表现与以前相同。 |
| 2021 年 3 月 25 日 | [数据修复 API](https://github.com/AdobeDocs/analytics-2.0-apis/blob/master/data-repair.md) 更新（过滤 URL、查询字符串、@ 符号等） |
| 2021 年 3 月 25 日 | 新的[使用情况日志 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/usage-logs.md) 文档 |
| **2021 年 2 月** | |
| 2021 年 2 月 4 日 | 组件选择：在[!UICONTROL 快速见解]中发现的下拉/放置区域组件已添加到[!UICONTROL 工作区]中的所有放置区域。通过此增强功能，您可以从兼容组件的下拉列表中进行选择，或继续将空间用作放置区域。 |
| **2021 年 1 月** | |
| 2021 年 1 月 14 日 | 向 Analytics 功能板文档添加了语言选择选项。 |
| 2021 年 1 月 14 日 | 新增有关如何通过引用公共图像 URL 将图像添加到工作区项目的文档。 |
| 2021 年 1 月 14 日 | 合并了工作区可视化源和设置管理器：用于可视化的[!UICONTROL 数据源]管理器（点）和设置管理器（齿轮）已合并为单个弹出框，因此可轻松地从同一位置管理源和设置。 |

### 2020 {#20}

| 功能 | 描述 |
| --- | --- |
| **2020 年 12 月** | |
| 2020 年 12 月 7 日 | 修改了所有相关页面以包含或替换“adobedc.net”端点。 |
| 2020 年 12 月 8 日 | 更新了工作区中的[创建新项目](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?lang=zh-Hans)页面。 |
| **2020 年 11 月** | |
| 2020 年 11 月 24 日 | 更新了工作区中的[面板概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans)页面。 |
| 2020 年 11 月 24 日 | 新的实施审查文档： <ul><li>[全面实施审查](https://experienceleague.adobe.com/docs/analytics/implementation/review/full-review.html?lang=zh-Hans)</li><li>[集中实施审查](https://experienceleague.adobe.com/docs/analytics/implementation/review/focused-review.html?lang=zh-Hans)</li></ul> |
| 2020 年 11 月 24 日 | 更新了 Analysis Workspace [可视化概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hans)页面。 |
| 2020 年 11 月 12 日 | 新增了有关[继承的 Adobe Analytics 实施](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/existing-implementation.html?lang=zh-Hans)的页面。 |
| 2020 年 11 月 2 日 | 更新了有关[用于分类的 FTP](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html?lang=zh-Hans) 的文档。 |
| **2020 年 10 月** | |
| 2020 年 10 月 23 日 | 工作区折线图可视化图表：[均线趋势线选项](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html?lang=zh-Hans)：此设置已添加到[!UICONTROL 折线图]可视化图表趋势线设置。均线也称为滚动平均值，它使用特定数量的数据点（由&#x200B;**[!UICONTROL 周期]**&#x200B;选择确定），对其求平均值，并将平均值用作折线中的点。 |
| 2020 年 10 月 23 日 | 工作区[性能帮助页面](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html?lang=zh-Hans)显示影响项目性能的不同因素以及指向优化提示的链接。 |
| 2020 年 10 月 23 日 | 向 Adobe Analytics 功能板文档添加了增强功能。在工作区中构建移动记分卡时，记分卡的样式现在与应用程序匹配。 |
| **2020 年 9 月** | |
| 2020 年 9 月 17 日 | [下载单个维度的 5 万个项目](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hans#download-items)：现在可以为自由格式表中的单个维度下载 50,000 个项目，并应用区段和过滤器。这允许您访问 Analysis Workspace 以外的 400 多行数据。 |
| 2020 年 9 月 17 日 | [折线图可视化图表的增强功能](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html?lang=zh-Hans)： <ul><li>可显示或隐藏任何[!UICONTROL 折线图]可视化图表的 X 轴和 Y 轴。如果想让[!UICONTROL 折线图]可视化图表显得更加紧凑，这项功能会特别有用。</li><li>您可以在任何折线图可视化图表上叠加最小值和最大值标签，以便快速突出显示量度中的高峰和低谷。</li><li>您可以在任何折线图可视化图表上叠加不同的回归趋势线，以便更轻松地查看数据趋势。相关选项包括[!UICONTROL 线性]、[!UICONTROL 对数]、[!UICONTROL 指数]、[!UICONTROL 幂]和[!UICONTROL 二次方程式]。</li></ul> |
| 2020 年 9 月 17 日 | 工作区中的新日期范围：我们新增了 5 个日期范围（最近 7 天整、最近 14 天整、最近 30 天整、最近 60 天整、最近 90 天整），这样从现在开始，您就可以选择不包含部分日期数据的日期范围 |
| 2020 年 9 月 17 日 | 新增有关[工作区中的“媒体并行查看者”面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers.html?lang=zh-Hans)的文档 |
| **2020 年 8 月** | |
| 2020 年 8 月 31 日 | 向 Cross-Device Analytics 中的[基于字段的拼合文档](https://experienceleague.adobe.com/docs/analytics/components/cda/field-based-stitching.html?lang=zh-Hans)添加了增强功能。 |
| **2020 年 7 月** | |
| 2020 年 7 月 21 日 | [跨设备分析](/help/components/cda/overview.md)的主要更新和修订。添加了[基于字段的拼合](/help/components/cda/field-based-stitching.md)。 |
| 2020 年 7 月 16 日 | 工作区中的新日期范围预设。添加了 4 个新的日期范围：（[!UICONTROL 本周/月/季度/年（不包括今天）]）。这允许您从不包括今天的部分日期数据的日期范围中进行选择。 |
| **2020 年 6 月** | |
| 2020 年 6 月 25 日 | 新增有关工作区中的[“快速见解”面板](/help/analyze/analysis-workspace/c-panels/quickinsight.md)的文档。它可为 Analysis Workspace 的非分析师和新用户了解如何快速轻松地回答业务问题提供指导。 |
| 2020 年 6 月 25 日 | 新增有关工作区中的[“Analytics for Target”面板](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)的文档。它可让您轻松自信地分析 Adobe Target 活动和体验。 |
| 2020 年 6 月 18 日 | 新增有关[归因：算法归因](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html?lang=zh-Hans)的文档 |
| 2020 年 6 月 18 日 | 新增有关[归因：自定义回溯时段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=zh-Hans#lookback-windows)的文档 |
| 2020 年 6 月 18 日 | 新增有关共享工作区项目的[项目角色](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans)的文档。现在，在共享工作区项目时，您可以根据希望收件人获得的项目体验为收件人分配以下三个项目角色中的一个角色：“编辑”、“复制”和“查看”。 |
| 2020 年 6 月 18 日 | 新增有关[“仅查看”工作区项目](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/view-only-projects.html?lang=zh-Hans)的文档。只能以“可查看”的形式将项目共享给用户。当具有查看角色的收件人打开共享项目时，他们将会获得较为受限的项目体验，即，无左边栏而且只能进行有限的交互。 |
| 2020 年 6 月 18 日 | 新增有关共享工作区项目的[项目角色](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans)的文档。现在，在共享工作区项目时，您可以根据希望收件人获得的项目体验为收件人分配以下三个项目角色中的一个角色：“编辑”、“复制”和“查看”。 |
| 2020 年 6 月 18 日 | 新增有关[协同编辑工作区项目](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans)的文档。添加到“可编辑”角色的收件人可以保存已共享给他们的项目。这同时适用于管理员和非管理员用户。 |
| **2020 年 5 月** |  |
| 2020 年 5 月 31 日 | 新增有关 [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 的文档 |
| 2020 年 5 月 21 日 | 新增有关 [Adobe Analytics 功能板](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=zh-Hans)的文档 |
| 2020 年 5 月 21 日 | 新增有关 Analysis Workspace 的[可访问性改进](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/aw-accessibility.html?lang=zh-Hans)（包括改进的键盘导航、颜色对比度和屏幕阅读器支持）的文档。 |
| **2020 年 4 月** |  |
| 2020 年 4 月 28 日 | 添加了有关[内容周转率](/help/components/metrics/content-velocity.md)￼量度的文档。 |
| 2020 年 4 月 16 日 | 有关如何自动从空白状态构建[!UICONTROL 自由格式表]的文档。以前，不能将组件直接拖放到空白项目或空白面板，而是必须先添加一个自由格式表。现在，您可以将组件直接拖放到空白项目或面板中，并且系统将以推荐的格式自动为您构建自由格式表。此外，改进了将混合组件类型（如维度与量度）一起拖放到空白[!UICONTROL 自由格式表]中时，对这些组件的处理方式。 |
| **2020 年 3 月** |  |
| 2020 年 3 月 12 日 | 添加了[将区段发布到 Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-publish.md) 的更新。 |
| 2020 年 3 月 12 日 | 更新了 CDA 拼合延迟。 |
| 2020 年 3 月 12 日 | 支持工作区中的多个报告包。您现在可以将多个报告包中的数据并入一个项目，以便并排查看。[了解详情...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=zh-Hans) |
| 2020 年 3 月 12 日 | 工作区中的培训教程模板。这个新的标准模板可指导您逐步了解在工作区中构建首个分析的常用术语和步骤。该模板可用作新建项目模式中的标准模板，并替换当前存在的示例项目，供列表中没有其他项目的新用户使用。[了解详情...](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) |
| **2020 年 2 月** |  |
| 2020 年 2 月 27 日 | 添加了有关 [Adobe Analytics Labs](/help/analyze/labs.md) 的文档。 |
| 2020 年 2 月 25 日 | 添加了 [`useLinkTrackSessionStorage`](/help/implement/vars/config-vars/uselinktracksessionstorage.md) 变量。 |
| 2020 年 2 月 20 日 | 适用于使用 Cross-Device Analytics 的组织的新工作区模板。此模板显示 CDA 在拼合访问次数方面的有效性，并且还指导您了解 CDA 独有的维度和量度知识。需要使用 CDA 的报告包。有关更多信息，请参阅[设置 Cross-Device Analytics](/help/components/cda/setup.md)。 |
| 2020 年 2 月 20 日 | 工作区中的新热键：<ul><li>折叠/展开所有面板：`alt + m`</li><li>折叠/展开活动面板: `alt + ctrl + m`</li><li>搜索左边栏: `ctrl + /`</li><li>移到下一个面板: `alt + Right Key`</li><li>移到上一个面板: `alt + Left Key`</li></ul>[了解详情...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=zh-Hans) |
| 2020 年 2 月 20 日 | 工作区增强功能： <ul><li>将面板或可视化图表放入工作区后，左边栏会自动切换到组件，以实现更加无缝的工作流程。</li><li>现在可以对模板组件进行操作（例如，标记、标记为收藏、已批准）。</li><li>过滤的量度和区段列表提供了 + 按钮，可在找不到所需内容时添加新组件。</li></ul> |
| 2020 年 2 月 20 日 | 工作区调试器已添加到“帮助”菜单，可让您根据调试工作区请求更加无缝地启用该调试器。[了解详情...](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |
| 2020 年 2 月 18 日 | 添加了 [`writeSecureCookies`](/help/implement/vars/config-vars/writesecurecookies.md) 变量。 |
| 2020 年 2 月 12 日 | 更新并重新整理了[营销渠道](/help/components/c-marketing-channels/c-getting-started-mchannel.md)文档。 |
| 2020 年 2 月 12 日 | 已将新热键添加到[此工作区页面](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=zh-Hans) |
| 2020 年 2 月 7 日 | 更新了[设置跨设备分析](/help/components/cda/setup.md)和[常见问题解答](/help/components/cda/faq.md)。 |
| 2020 年 2 月 4 日 | 完全重写[实施用户指南](/help/implement/home.md)。 |
| 2020 年 1 月 22 日 | 更新了“自由格式表”页面，现在包含有关新的[自由格式表生成器](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)的信息。 |
| **2020 年 1 月** | |
| 2020 年 1 月 24 日 | 更新了工作区中的[行设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=zh-Hans#cja-workspace?lang=zh-Hans)页面。 |
| 2020 年 1 月 16 日 | 新增有关[自由格式表生成器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=zh-Hans)的文档。启用表生成器后，您可以通过拖放多个维度、细分、量度和区段来构建可解答更复杂业务问题的表。数据不会立即更新，相反，单击&#x200B;**[!UICONTROL 生成]**&#x200B;后才会进行更新，这样可在您知道自己要构建什么表的情况下节省您的时间。此外，此功能还提供：<ul><li>**预览**：您可以先预览表的格式，然后再花费时间渲染实际数据。</li><li>**灵活的行和划分设置**：您可以为每个维度行设置行级别和划分级别。以前，工作区施加了一些默认值，这些默认值在返回数据之前无法更改。</li><li>**按状态划分**：您可以将维度行设置为始终&#x200B;_按状态划分_&#x200B;而不是&#x200B;_按特定项目_（默认值）划分。</li><li>**手动静态行排序**：您可以手动对静态行进行排序，以使表行完全按照您的需要显示。以前，静态行只能按量度列或按字母顺序排序。</li></ul> |
| 2020 年 1 月 13 日 | 添加了 [Adobe Analytics 和浏览器 Cookie](/help/technotes/cookies/cookies.md)。 |
| 2020 年 1 月 13 日 | 修改了[我应该使用哪种 Adobe Analytics 工具](/help/analyze/get-started/which-analytics-tool.md)页面。 |

### 2019 {#19}

| 功能 | 描述 |
| --- | --- |
| 2020 年 12 月 19 日 | 已将默认 [FTP 数据存储限制](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-limits.html?lang=zh-Hans)更改为 10 GB。 |
| 2019 年 11 月 29 日 | 全面修订了[数据馈送文档](/help/export/analytics-data-feed/data-feed-overview.md) |
| 2019 年 11 月 25 日 | 新增了有关强制 IP 登录限制终止使用的主题。 |
| 2019 年 11 月 21 日 | 新增了 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=zh-Hans) 文档集 |
| 2019 年 11 月 21 日 | 更新了 [Audience Analytics 工作流程常见问题解答](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html?lang=zh-Hans)以指示 LiveStream 中的可用性。 |
| 2019 年 10 月 25 日 | 更新了 [Adobe Analytics 关键概念](/help/technotes/terms.md)页面。 |
| 2019 年 10 月 10 日 | 更新了自由格式表总计：它们现在包含两个总计，即&#x200B;**[!UICONTROL 表总计]**&#x200B;和&#x200B;**[!UICONTROL 全部总计]**。表格总计行会将已应用的[报告过滤器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html?lang=zh-Hans)计入在内。以前，只有区段会影响总数的计算。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=zh-Hans)<br/>，此外，**[!UICONTROL ￼显示总数]**&#x200B;和&#x200B;**[!UICONTROL 显示总计]**&#x200B;选项已添加到&#x200B;**[!UICONTROL 列设置]**&#x200B;中。<br/>鉴于自由格式表的这项变化，与之相关的可视化图表（例如关联的&#x200B;**[!UICONTROL 摘要数字]**&#x200B;可视化图表）也将进行相应的更新，导出的 CSV 和 PDF 数据同样也会更新。 |
| 2019 年 10 月 10 日 | 在 Workspace 中，已将轻松地删除“未指定（无）”作为一个选项添加到报告过滤器。 |
| 2019 年 10 月 10 日 | 在工作区中，紫色粒度组件（分钟、小时、天、周、月、季度、年）已被弃用。即使之前使用了某个紫色时间组件，您也&#x200B;**无需执行任何操作**。<br/>此外，根据这项变化，紫色的&#x200B;**[!UICONTROL 时间]**&#x200B;部分已重命名为&#x200B;**[!UICONTROL 日期范围]**。 |
| 2019 年 10 月 1 日 | 新增有关[工作区总计](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/workspace-totals.html?lang=zh-Hans#cja-workspace?lang=zh-Hans)的文章。 |
| 2019 年 9 月 28 日 | 新增了有关[用于 Javascript 实施的配置变量](/help/implement/vars/config-vars/configuration-variables.md)的文章 |
| 2019 年 9 月 19 日 | 修订了分段文档以说明[逻辑组容器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html?lang=zh-Hans#logic-group-containers?lang=zh-Hans)。 |
| 2019 年 9 月 12 日 | 新增了[历程 IQ：跨设备分析](/help/components/cda/overview.md)文档 |
| 2019 年 9 月 12 日 | 更新了[计算量度总计](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html?lang=zh-Hans)文档。 |
| 2019 年 8 月 28 日 | 新增了有关[用于 Analytics 的渐进式 Web 应用程序 (PWA)](/help/technotes/pwa.md) 的文章 |
| 2019 年 8 月 8 日 | 有关[计算量度合计](/help/components/c-calcmetrics/cm-totals.md)的新文章 |
| 2019 年 8 月 8 日 | 关于[已启用时间戳的会话数据](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)的说明 | 2019 年 8 月 8 日 | 在 Workspace 中，Adobe 将可放入静态下拉过滤器的项数限制从 50 提高到 200。此增强功能适用于各种用例，例如将所有国家/地区 (195) 添加到过滤器，或将所有美国州和省 (52) 添加到过滤器。 |
| 2019 年 8 月 2 日 | [Analytics 词汇表](/help/technotes/terms.md)的主要更新 |
| 2019 年 7 月 22 日 | 将“Magento：营销和商务”模板添加到 [Analysis Workspace 模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)文档。 |
| 2019 年 7 月 18 日 | 更新了[同类群组表格设置](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。 |
| 2019 年 7 月 18 日 | 在工作区中的左边栏中，用户现在可以选择&#x200B;_显示过去 18 个月内的项目_。以前，回看周期最长为 6 个月。这样，用户就可以更轻松地比较去年（最长 18 个月前）的页面或营销活动。 |
| 2019 年 7 月 18 日 | 有关在 Analysis Workspace 中新增的名为[“Magento：营销与商务”](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=zh-Hans) 的工作区模板的文档。它专为 Magento 电子商务客户设计，不过任何零售商都可使用它来获得有关其商务活动的独特洞察。 |
| 2019 年 6 月 13 日 | 工作区中的左边栏搜索新增了开箱即用的过滤器。除了您现在看到的这些过滤器（维度、量度、已批准等）之外，还新增了一些过滤器（例如计算量度、客户属性、eVar、Prop、视频等）以更便于查找所需的组件。 |
| 2019 年 6 月 4 日 | 编写了题为[从第三方分析平台转换到 Adobe Analytics](/help/technotes/ga-to-aa/home.md) 的新指南。 |
| 2019 年 5 月 30 日 | 全面修订了[数据馈送列参考](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。 |
| 2019 年 5 月 9 日 | 流量可视化图表设置中添加了一个新设置：包含重复实例。请参阅[流量设置](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| 2019 年 4 月 11 日 | 工作区增强功能优化最佳实践：[优化性能](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md) |
| 2019 年 4 月 11 日 | 更新了[优化工作区性能](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)。 |
| 2019 年 3 月 14 日 | 对[地区数据收集](/help/technotes/rdc/regional-data-collection.md)进行了重大更新。 |
| 2019 年 2 月 7 日 | 对[常规帐户设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)中的“将 IP 地址的最后一个八位字节替换为 0”设置和“IP 模糊处理”设置进行了小幅更新。 |
| 2019 年 2 月 1 日 | 对 [getPercentPageViewed](../implement/vars/plugins/getpercentpageviewed.md) 实施插件进行了重大更新。 |
| 2019 年 1 月 17 日 | [同类群组分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) - 对同类群组分析进行重大改进后，您能够：<ul><li>应用区段包含并单独返回量度。 </li><li>显示流失率而不是保留率。</li><li>显示延时表（包含事件之前和之后经过的时间）。</li><li>自定义同类群组维度（根据 eVar 而不只是时间对访客进行分组）。</li><li>进行滚动式同类群组计算：根据先前的时间段而不是原始同类群组来计算维系率/流失率。 </li><li>将多个量度添加到包含和回访字段中，并应用区段。（不支持计算量度）</li></ul> |
| 2019 年 1 月 17 日 | [视图密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md)。此新设置可减少左边栏、自由格式表和同类群组表中的垂直边距，从而使您能够在单个屏幕上查看更多数据。可通过项目 > 项目信息和设置进行访问。 |
| 2019 年 1 月 17 日 | [在归因中支持多值变量](/help/analyze/analysis-workspace/attribution/overview.md)。Analytics 中的某些维度可以在单次点击中包含多个值，例如 listVar、产品变量、列表属性或推销 eVar。Analysis Workspace 使您可将归因应用于点击级别的任何此类变量。 |
