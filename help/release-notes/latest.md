---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a4efa48df735eacbda0f53ba30064da7d8f71028
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 51%

---

# 当前 Adobe Analytics 发行说明（2024 年 5 月）

**上次更新**：2024年5月15日

这些发行说明涵盖2024年5月15日至6月的发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **关于从Adobe Analytics升级到Customer Journey Analytics的新文档** | 对于从Adobe Analytics升级到Customer Journey Analytics的组织，根据组织当前的Adobe Analytics实施和长期目标，需要牢记有多个升级选项和许多注意事项。 现提供新的文档资源来帮助您更好地理解：<ul><li>现有的各种升级路径</li><li>根据组织当前的 Adobe Analytics 实施情况，有哪些升级路径可用</li><li>每种升级路径的优缺点</li><li>每种升级路径的分步指导</li><li>处理历史数据的注意事项</li></ul>[Customer Journey Analytics升级入门](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 现在可用 |
| **设置 `contextData` 通过XDM显示的字段** | 通过体验Edge Network将数据发送到Adobe Analytics的客户可以 [设置上下文数据值](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/contextdata) 直接在XDM或有效负载的“数据”部分中访问。 |  | 现在可用 |
| **Analytics实时报表2.0 API** | Adobe Analytics中新的实时报表API 2.0改进了客户集成并提供快速的报表结果。 这些结果可以通过编程方式用于基本、趋势和划分报表。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 2024年5月30日 |
| **流媒体：使用Web SDK将Web数据发送到Adobe Experience PlatformEdge Network** | 您现在可以使用Adobe Experience Platform Web SDK将流媒体Web数据发送到Adobe Experience PlatformEdge Network。 通过此增强功能，可构建更个性化的促销活动并提供更个性化的内容，从而产生要报告的更多跟踪数据。<p>这项更改为所有平台解决方案(如Customer Journey Analytics、Adobe实时CDP、Adobe Journey Optimizer和事件转发)的Web实施提供了统一的收集方法。 以前，将流媒体Web数据发送到Edge Network的唯一方法是使用Media Edge API。 [了解详情](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | | 2024 年 5 月 31 日 |
| **增大默认低流量阈值** | 在 **2024 年 4 月中旬**，Adobe 将开始增大默认报告包低流量阈值，如下所示：![低流量阈值](assets/thresholds.png) 这只会影响当前设置的小于新阈值的变量。这些更改将逐步进行，我们预计这项工作将在&#x200B;**五月底**&#x200B;之前完成。在实施这些增加时，您可能会注意到高基数变量的变化：<ul><li>更多维度值可用于报告。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报告包可能包含更多数据。</li><li>分类导出可能包含更多数据。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月 31 日 |
| **Activity Map减少对Web SDK的服务器调用** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。此增强功能采用一些链接事件并将它们打包到下一次点击中，这与AppMeasurement处理事件的方式类似。 （需遵循的文档） |  | 2024 年 5 月 31 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-343186、AN-344711、AN-344856、AN-345094、AN-345179、AN-346265、AN-345288、AN-346339、AN-346560、AN-347572、AN-347681、AN-347768、AN-348024
* 修复了以下Data Warehouse问题：AN-346789、AN-347031、AN-347568；
* 修复了以下数据馈送问题：AN-343616、AN-345831、AN-345988、AN-346124、AN-346232、AN-346972、AN-347680、AN-347755、AN-347954
* 修复了以下数据源问题：AN-347890；
* 修复了以下Analysis Workspace问题：AN-321503、AN-343103、AN-343471、AN-345171、AN-345223、AN-345912、AN-346026、AN-346330、AN-346839、AN-347679
* 修复了以下A4T问题：AN-345118；

### 其他 Analytics 修复

AN-327749、AN-332949、AN-342881、AN-343171、AN-343708、AN-344034、AN-345559、AN-346023、AN-346230、AN-346330、AN-346469、AN-346606、AN-346750、AN-346973、AN-347026、AN-347110、AN-347439；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **ISO区域更新** | 2024年5月10日 | Adobe将于2024年6月7日执行2024年ISO区域更新。 预计在此版本之后将看到较小的地理信息（地区）更新。 |
| **保存的`cust_visids`** 13 个月有效期 | 2024 年 3 月 20 日 | 即将发布的 Analytics Hit 处理引擎（预计于 4 月或 5 月发布）将开始对保存的 `cust_visids` 强制执行 13 个月的有效期。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。目前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期。在此版本中，如果自以下时间以来已过13个月或更长时间 `visid_high/visid_low` 曾经 `cust_visid` 在点击时，映射过期。 |

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
