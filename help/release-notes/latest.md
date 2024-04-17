---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 627a813d0d5595521d72f0cf832b3a1ceb7655f8
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 50%

---

# 当前 Adobe Analytics 发行说明（2024 年 4 月）

**上次更新**：2024年4月17日

这些发行说明涵盖2024年4月17日至5月的发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **流媒体：将Roku数据发送到Adobe Experience PlatformEdge Network** | 现在，当 [使用Experience PlatformEdge安装Media Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)中，您可以使用Adobe Experience Platform Roku SDK将流媒体数据发送到Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **改进了Web SDK迁移工作流** | Adobe Experience Platform数据收集现在自动将许多字段从数据对象直接映射到Adobe Analytics。 此改进的工作流具有以下优势：<ul><li>它允许您的组织迁移到Web SDK，而无需担心创建或遵守 [!UICONTROL XDM架构]. 请参阅 [数据对象变量映射](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) 以了解更多信息。 （更多文档链接随后提供）</li><li>迁移到Web SDK后，贵组织可以更好地从Adobe Analytics迁移到Customer Journey Analytics。 这是因为Web SDK允许更无缝地迁移到Customer Journey Analytics。</li></ul> （有关此迁移选项和其他迁移选项的更多信息即将发布。） |  | 2024 年 4 月 |
| **仅用于项目的权限增强 [!UICONTROL 工作区] 组件** | 以前，如果用户（用户A）与其他用户（用户B）共享项目，并授予用户B编辑项目的权限，则用户B将能够编辑项目。 但是，用户B无法编辑 [!UICONTROL 快速区段] 嵌入到项目中。 该限制现已移除 — 用户B可以编辑 [!UICONTROL 快速区段] 以及嵌入到共享项目中的其他仅用于项目的组件。 |  | 2024 年 4 月 17 日 |
| **将相同的云帐户用于 [!UICONTROL 数据馈送]， [!UICONTROL Data Warehouse]、和 [!UICONTROL 分类集]** | 您创建的云帐户和位置现在可用于导出数据(使用 [!UICONTROL 数据馈送] 和 [!UICONTROL Data Warehouse])并导入数据(使用 [!UICONTROL 分类集])。<p> **配置帐户时的更改：** 用户可以 [配置云导入和导出帐户](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) 和 [配置云导入和导出位置](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations) 的任何其他资源：<ul><li>使用导入数据 [!UICONTROL 分类集]</li><li>导出数据，使用 [!UICONTROL 数据馈送]</li><li>导出数据，使用 [!UICONTROL Data Warehouse].</li></ul><p>**管理帐户时的更改**：用户可以使用 [位置](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) 页面(在 [!UICONTROL 组件] >洛克查看和管理其创建的所有帐户和位置，而不管这些帐户和位置是在何处创建的。 <p>以前， [!UICONTROL 位置] 页面仅适用于创建用于导入数据的帐户 [!UICONTROL 分类集].</p> | | 2024 年 4 月 17 日 |
| **管理员可以管理其组织中的所有位置和帐户** | “位置”选项卡（在“组件”>“位置”页面）上的新选项允许管理员查看和管理组织中的所有位置。<p>上的新选项 [位置](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) accounts选项卡（位于Components > Locations页面上）允许管理员查看和管理组织中的所有帐户。</p> <p>以前，管理员只能查看和管理他们创建的位置和帐户。</p> |  | 2024 年 4 月 17 日 |
| **增大默认低流量阈值** | 在 **2024 年 4 月中旬**，Adobe 将开始增大默认报告包低流量阈值，如下所示：![低流量阈值](assets/thresholds.png) 这只会影响当前设置的小于新阈值的变量。这些更改将逐步进行，我们预计这项工作将在&#x200B;**五月底**&#x200B;之前完成。在实施这些增加时，您可能会注意到高基数变量的变化：<ul><li>更多维度值可用于报告。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报告包可能包含更多数据。</li><li>分类导出可能包含更多数据。</li></ul> | 2024 年 4 月中旬 | 2024年5月31日 |
| **Activity Map 减少了 Web SDK 服务器调用次数** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。 <p>此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。</p> |  | 2024年5月1日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-343439、AN-343503、AN-343504、AN-343986、AN-344262、AN-344564、AN-345204、AN-345234
* 修复了以下分类规则生成器问题：AN-341488；AN-342501；AN-345751
* 修复了以下智能警报问题：AN-343466；
* 修复了以下分段问题：AN-342313
* 修复了以下Data Warehouse问题：AN-344292
* 修复了以下数据馈送问题：AN-339545、AN-340092、AN-342124、AN-342862、AN-343737、AN-344035、AN-344329、AN-344703、AN-344721、AN-344940、AN-345180、AN-345196、AN-345225、AN-345236、AN-345326、AN-345631、AN-345659、AN-
* 修复了以下数据源问题：AN-343541
* 修复了以下Analysis Workspace问题：AN-336303、AN-336472、AN-338422、AN-338556、AN-339718、AN-340147、AN-340301、AN-340421、AN-340951、AN-341172、AN-342905、AN-342909、AN-343448、AN-343570、AN-344050、AN-344182、AN-344763、AN-344768；
* 修复了以下Analytics管理问题：AN-342519、AN-342523、AN-343623、AN-343882、AN-344237、AN-344829、AN-345235；
* 修复了以下A4T问题：AN-341619；AN-344402
* 修复了以下移动设备应用程序问题：AN-342010

### 其他 Analytics 修复

AN-336099、AN-337474、AN-337993、AN-339718、AN-339901、AN-340014、AN-341356、AN-343021、AN-343102、AN-343353、AN-343416、AN-340014、AN-344037、AN-344525、AN-345737

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **保存的`cust_visids`** 13 个月有效期 | 2024 年 3 月 20 日 | 即将发布的 Analytics Hit 处理引擎（预计于 4 月或 5 月发布）将开始对保存的 `cust_visids` 强制执行 13 个月的有效期。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。目前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期。在此版本中，如果自 `visid_high/visid_low` 点击 `cust_visid` 以来已经过去了 13 个月或更长时间，则映射将会过期。 |
| **添加了 Adobe API 对象成员** | 2024 年 1 月 17 日 | Adobe 可能会随时无通知或在版本控制中无变更地将可选的请求和响应成员（名称/值对）添加到现有的 API 对象。Adobe 建议您参考与我们的 API 集成的任何第三方工具的 API 文档，以便在处理过程中忽略不了解的此类添加。如果正确实施，则此类添加应为不令您的实施发生中断的更改。如果没有首先通过发行说明提供标准通知，Adobe 不会删除参数或添加所需参数。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2023 年发行说明](/help/release-notes/2023.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
