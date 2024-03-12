---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 3c6e11dd9d0044dbf79fa0ba97e55a547966d120
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 99%

---

# 当前的 Adobe Analytics 发行说明（2024 年 2 月）

**上次更新日期**：2024 年 2 月 21 日

这些发行说明涵盖 2024 年 2 月 14 日至 2024 年 3 月 11 日的发行期。Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurement 更新** | [AppMeasurement 版本 v2.26.0](/help/implement/appmeasurement-updates.md) 现已推出。 | | 2024 年 3 月 4 日 |
| **Data Warehouse 更新** | Data Warehouse 现在有以下改进：<ul><li>在创建 Data Warehouse 请求时，用户现在可通过启用名为&#x200B;[!UICONTROL **提供给组织中的用户**]&#x200B;的新切换开关，将请求提供给组织中的所有用户。<p>有关详细信息，请参阅 [Data Warehouse 请求常规设置](/help/export/data-warehouse/create-request/dw-general-settings.md)。</p></li><li>在创建或管理 Data Warehouse 报告目标时，系统管理员现在可通过启用名为&#x200B;[!UICONTROL **显示所有目标**]&#x200B;的切换开关，显示组织中的用户创建的帐户和位置。<p>有关详细信息，请参阅[配置 Data Warehouse 请求的报告目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。</p></li> | 不适用 | 2024 年 1 月 10 日 |
| **关键量度摘要可视化的更新** | 在使用关键量度摘要可视化时，根据您选择的“比较日期范围”选项是相对于主要日期范围还是固定日期，现在可自动更新比较日期范围。[了解详情](/help/analyze/analysis-workspace/visualizations/key-metric.md)。 | 不适用 | 2024 年 1 月 17 日 |
| **Data Warehouse API 文档** | 请参阅 [Adobe Analytics Data Warehouse API 2.0](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Warehouse%20APIs#/Data%20Warehouse%20Scheduled%20Requests%20API) 以了解更多信息。转到[!UICONTROL 选择定义]，然后选择 [!UICONTROL Data Warehouse API]。 | | 2024 年 2 月 19 日 |
| **Web SDK 的 Activity Map，无额外费用** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。 |  | 2024年4月3日 |
| **增大默认低流量阈值** | 在 **2024 年 4 月中旬**，Adobe 将开始增大默认报表包低流量阈值，如下所示：![低流量阈值](assets/thresholds.png) 这只会影响当前设置的小于新阈值的变量。这些更改将逐步进行，我们预计这项工作将在&#x200B;**五月底**&#x200B;之前完成。在实施这些增加时，您可能会注意到高基数变量的变化：<ul><li>更多维度值可用于报告。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报表包可能包含更多数据。</li><li>分类导出可能包含更多数据。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月底 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-319515; AN-337559；AN-338149；AN-338702；AN-338769；AN-338891；AN-339327；AN-339649；AN-339668；AN-339669；AN-339776；AN-339822；AN-340017；AN-340202；AN-340476；
* 修复了以下分类规则生成器问题：AN-338385；AN-338399；AN-338592；AN-338810；AN-338893；AN-339431；AN-339894；AN-339933；AN-340201；AN-340309；
* 修复了以下 A4T 问题：AN-334830；AN-336194；AN-338309；AN-338650；
* 修复了以下数据收集问题：AN-339323
* 修复了以下 Data Warehouse 问题：AN-335542；AN-331425；AN-337215；AN-338445；AN-338643；AN-338651；AN-339461；AN-340066；AN-340207；AN-340460
* 修复了以下数据馈送问题：AN-335952；AN-338653；AN-339508；AN-339681；AN-340418
* 修复了以下数据源问题：AN-338648
* 修复了以下 Analysis Workspace 问题：AN-326509；AN-336186；AN-336190；AN-336309；AN-337922；AN-338094；AN-338323；AN-338556；AN-339600；AN-340445

### 其他 Analytics 修复

AN-328239；AN-332908；AN-335449；AN-335517；AN-336075；AN-336100；AN-336128；AN-338088；AN-338270；AN-338393；AN-338494；AN-339326；AN-339742；AN-339883；AN-340419；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 添加了 Adobe API 对象成员 | 2024 年 1 月 17 日 | Adobe 可能会随时无通知或在版本控制中无变更地将可选的请求和响应成员（名称/值对）添加到现有的 API 对象。Adobe 建议您参考与我们的 API 集成的任何第三方工具的 API 文档，以便在处理过程中忽略不了解的此类添加。如果正确实施，则此类添加应为不令您的实施发生中断的更改。如果没有首先通过发行说明提供标准通知，Adobe 不会删除参数或添加所需参数。 |
| `getPageLoadTime` 插件被弃用 | 2024 年 1 月 10 日 | 不再支持此插件。其代码利用了 performance.timing 方法，而（据 MDN 称）该方法已被[弃用](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)。更新插件的工作已经开始。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.25.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2023 年发行说明](/help/release-notes/2023.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
