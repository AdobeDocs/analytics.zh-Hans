---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4633225cc35658a7de39a40cd77df00137a54461
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 96%

---

# 当前 Adobe Analytics 发行说明（2024 年 6 月）

**上次更新**：2024年6月26日

这些发行说明涵盖 2024 年 6 月 12 日至 7 月的发行期。Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在下拉筛选条件中选择多个字段** | 当下拉筛选条件中添加多个字段时，用户现在可以一次选择多个字段。面板经过过滤，可包含任何选定的字段。 <p>以前，用户在下拉筛选条件中一次只能选择一个字段。</p><p>有关详细信息，请参阅[面板概述](/help/analyze/analysis-workspace/c-panels/panels.md)中的[静态下拉区段](/help/analyze/analysis-workspace/c-panels/panels.md#static-drop-down-segments)。</p><p>[观看此功能的视频演示](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | 2024 年 6 月 19 日 |
| **Workspace 项目目录** | 现在可以为项目提供新的目录。目录提供了链接，使用户能够快速跳转到项目内的面板和可视化内容。可以为单个项目或给定用户的所有项目启用目录。<p>有关详细信息，请参阅[项目目录](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)。</p><p>[观看此功能的视频演示](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | 2024 年 6 月 19 日 |
| **为自由格式表中的维度项目创建超链接** | 您可以为一个或多个维度项目创建超链接，使其在 Analysis Workspace 中的自由格式表中可点击。 <p>您可以为具有 URL 值的维度项目创建超链接，也可以为具有非 URL 值的维度项目创建自定义 URL。</p><p>您可以使用变量为多个维度项目创建动态自定义 URL。变量可以引用维度项目的值，也可以引用细分维度。</p><p>有关详细信息，请参阅[在自由格式表中为维度创建超链接](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。</p><p>[观看此功能的视频演示](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | 2024 年 6 月 19 日 |
| **管理员设置控制用于导出和导入的帐户和位置** | 位置管理器中[新的“管理设置”选项卡使管理员](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only)可以控制用户是否可以创建和编辑帐户和位置。当用户[配置 cloud 导入和导出账户](/help/components/locations/configure-import-accounts.md)以及[配置 cloud 导入和导出位置](/help/components/locations/configure-import-locations.md)时，这些设置适用。 <p>管理员还可以限制用户可以创建和使用的帐户类型（Google Cloud Platform、Azure RBAC、Amazon S3 等）。</p><p>以前，任何用户都可以创建、编辑和使用任何类型帐户的帐户和位置。</p> | 2024 年 6 月 12 日 | 2024 年 6 月 20 日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者以及系统管理员可以编辑和删除帐户和位置。<p>以前，帐户和位置只能由创建它们的用户使用。</p><p>当用户[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)以及[配置云导入或导出位置时，这些设置适用](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-locations)。 </p> | 2024 年 6 月 12 日 | 2024 年 6 月 20 日 |
| **Activity Map 减少了 Web SDK 服务器调用次数** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。 <p>（更新文档链接见下文）</p> | 开放Beta 2024年7月10日开始 | 待定 |
| **新数据源 API 指南** |  [Adobe Analytics 2.0 Data Sources API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-sources/) 端点提供创建、查看、删除和上传到 Data Sources 帐户的方法。 |  | 现在可用 |
| **分类 API 指南中的新方法** | 分类 API 指南中添加了两种检索文件分区的新方法。<ul><li>[获取分类作业文件分区](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-job-file-partition-list)</li><li>[获取分类导出作业文件部分](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-export-job-file-part)</li></ul> |  | 现在可用 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-347682；AN-348396；AN-348625；AN-348668；AN-348926；AN-348936；AN-349040；AN-349191；AN-349195；AN-349443；AN-349697；AN-349758；AN-349862；AN-350051；AN-350054；AN-350208；AN-350497；AN-350525；AN-351067
* 修复了以下 Data Warehouse 问题：AN-346862；AN-349409；AN-349926；AN-350629；AN-350996
* 修复了以下数据馈送问题：AN-346727；AN-348282；AN-348334；AN-348725；AN-348726；AN-348823；AN-349081；AN-349207；AN-349307；AN-349539；AN-349710；AN-349729；AN-349742；AN-349878；AN-349943；AN-350527；
* 修复了以下数据源问题：AN-350038
* 修复了以下 Analysis Workspace 问题：AN-342953；AN-346346；AN-349590；AN-349717；AN-350057；AN-350697；AN-350904
* 修复了以下 Report Builder 问题：AN-348903；AN-350691
* 修复了以下 A4T 问题：AN-347690；AN-350853

### 其他 Analytics 修复

AN-346470；AN-346850；AN-347227；AN-348145；AN-348564；AN-349001；AN-349008；AN-349211；AN-349719；AN-350523；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **保存的`cust_visids`** 13 个月有效期 | 2024 年 5 月 22 日 | 即将发布的 Analytics Hit 处理引擎&#x200B;**（预计于 2024 年 7 月发布）**&#x200B;将开始对保存的 `cust_visids` 强制执行 13 个月的有效期。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。目前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期。在此版本中，如果自 `visid_high/visid_low` 点击 `cust_visid` 以来已经过去了 13 个月或更长时间，则映射会过期。 |
| **ISO 区域更新** | 2024 年 5 月 10 日 | Adobe 将在 2024 年 6 月 7 日执行 2024 年 ISO 区域更新。预计在此次发布后将看到少量地理信息更新（区域）。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [流媒体收集加载项发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
