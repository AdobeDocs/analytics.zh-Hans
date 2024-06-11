---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: aabf3b2ef75206938f559af9376e5af483687dbf
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 97%

---

# 当前 Adobe Analytics 发行说明（2024 年 5 月）

**上次更新时间**：2024 年 6 月 3 日

这些发行说明涵盖 2024 年 5 月 15 日至 6 月的发行期。Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **有关从 Adobe Analytics 升级到 Customer Journey Analytics 的新文档** | 对于从 Adobe Analytics 升级到 Customer Journey Analytics 的组织，需要考虑组织当前的 Adobe Analytics 实施和长期目标，有多种升级选项和许多注意事项需要牢记。现提供新的文档资源来帮助您更好地理解：<ul><li>现有的各种升级路径</li><li>根据组织当前的 Adobe Analytics 实施情况，有哪些升级路径可用</li><li>每种升级路径的优缺点</li><li>每种升级路径的分步指导</li><li>处理历史数据的注意事项</li></ul>[开始升级到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 现在可用 |
| **通过 XDM 设置 `contextData` 字段** | 通过 Experience Edge Network 向 Adobe Analytics 发送数据的客户可以[直接在 XDM 或负载的“数据”部分设置上下文数据值](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/vars/page-vars/contextdata)。 |  | 现在可用 |
| **Analytics 实时报告 2.0 API** | Adobe Analytics 中的新实时报告 API 2.0 改善了客户集成，并提供快速的报告结果。这些结果可以通过编程用于基本报告、趋势报告和划分报告。[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 2024 年 5 月 30 日 |
| **流媒体：使用 web SDK 将 web 数据发送到 Adobe Experience Platform Edge Network** | 您现在可以使用 Adobe Experience Platform Web SDK 将流媒体 Web 数据发送到 Adobe Experience Platform Edge Network。通过此增强功能，您可以构建更加个性化的活动并提供更加个性化的内容，从而生成更多的跟踪数据以供报告使用。<p>此更改为所有 Platform 解决方案（例如 Customer Journey Analytics、Adobe Real-time CDP、Adobe Journey Optimizer 和事件转发）的 Web 实施提供了统一的收集方法。以前，将流媒体网络数据发送到 Edge Network 的唯一方法是使用 Edge Network API。 <p>[了解详情](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 2024 年 5 月 29 日 |
| **增大默认低流量阈值** | 在 **2024 年 4 月中旬**，Adobe 将开始增大默认报告包低流量阈值，如下所示：![低流量阈值](assets/thresholds.png) 这只会影响当前设置的小于新阈值的变量。这些更改将逐步进行，我们预计这项工作将在&#x200B;**五月底**&#x200B;之前完成。在实施这些增加时，您可能会注意到高基数变量的变化：<ul><li>更多维度值可用于报告。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报告包可能包含更多数据。</li><li>分类导出可能包含更多数据。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月 31 日 |
| **管理员设置控制用于导出和导入的帐户和位置** | 位置管理器中新的“管理设置”选项卡使管理员可以控制用户是否可以创建和编辑帐户和位置。当用户配置 cloud 导入和导出账户以及配置 cloud 导入和导出位置时，这些设置适用。 <p>管理员还可以限制用户可以创建和使用的帐户类型（Google Cloud Platform、Azure RBAC、Amazon S3 等）。</p><p>以前，任何用户都可以创建、编辑和使用任何类型帐户的帐户和位置。</p><p>有关更多信息，请参阅 [配置公司范围的设置（仅限管理员）](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) 在 [位置管理器](/help/components/locations/locations-manager.md).</p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者以及系统管理员可以编辑和删除帐户和位置。<p>以前，帐户和位置只能由创建它们的用户使用。</p><p>当用户配置云导入和导出帐户以及配置云导入或导出位置时，这些设置适用。 </p> <p>有关更多信息，请参阅 [配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md) 和 [配置云导入和导出位置](/help/components/locations/configure-import-locations.md).</p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **Activity Map 减少了 Web SDK 服务器调用次数** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。 <p>（更新文档链接见下文）</p> | Beta 公测将于 2024 年 6 月 19 日开始 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-343186; AN-344711; AN-344856; AN-345094; AN-345179; AN-346265; AN-345288; AN-346339; AN-346560; AN-347572; AN-347681; AN-347768; AN-348024
* 修复了以下 Data Warehouse 问题：AN-346789; AN-347031; AN-347568;
* 修复了以下数据馈送问题：AN-343616；AN-345831；AN-345988；AN-346124；AN-346232；AN-346972；AN-347680；AN-347755；AN-347954
* 修复了以下数据源问题：AN-347890；
* 修复了以下 Analysis Workspace 问题：AN-321503；AN-343103；AN-343471；AN-345171；AN-345223；AN-345912；AN-346026；AN-346330；AN-346839；AN-347679
* 修复了以下 A4T 问题：AN-345118；

### 其他 Analytics 修复

AN-327749；AN-332949；AN-342881；AN-343171；AN-343708；AN-344034；AN-345559；AN-346023；AN-346230；AN-346330；AN-346469；AN-346606；AN-346750；AN-346973；AN-347026；AN-347110；AN-347439

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

* [以前的 2023 年发行说明](/help/release-notes/2023.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
