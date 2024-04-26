---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7468463e2fe1de16221b4528919b6abd6c8aedcb
workflow-type: ht
source-wordcount: '1445'
ht-degree: 100%

---

# 当前 Adobe Analytics 发行说明（2024 年 4 月）

**上次更新时间**：2024 年 4 月 17 日

这些发行说明涵盖 2024 年 4 月 17 日至 2024 年 5 月的发行期。Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **流媒体：将 Roku 数据发送到 Adobe Experience Platform Edge Network** | 现在，当 [使用 Experience Platform Edge 安装 Media Analytics ](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)时，您可以使用 Adobe Experience Platform Roku SDK 将流媒体数据发送到 Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **改进了 Web SDK 迁移的工作流程** | 数据流现在会自动将字段从 Web SDK 数据对象直接映射到 Adobe Analytics。[数据对象映射](/help/implement/aep-edge/data-var-mapping.md)类似于 [XDM 对象映射](/help/implement/aep-edge/xdm-var-mapping.md)，但不需要 XDM 架构。这种改进的工作流程具有以下优点：<ul><li>它会延迟要求使用架构，直到您准备好将数据发送到 Adobe Experience Platform。如果在实施迁移中的这个阶段需要一个架构，您则需要使用基于 Adobe Analytics 字段的架构。Adobe Experience Platform 服务（例如 Customer Journey Analytics）没有 prop 或 eVar 的概念。如果您的组织将来想要使用自己的架构，则以分析为中心的架构可能会带来困难。</li><li>在对 Web SDK 进行实施更改后，您的组织将能够更好地从 Adobe Analytics 迁移到 Customer Journey Analytics。如果您使用 Web SDK 将数据发送到 Adobe Analytics，则无需进行其他实施更改即可将数据发送到 Adobe Experience Platform。相反，您可以使用数据准备功能将数据对象字段映射到您的 XDM 模式。</li></ul>请参阅[从 Adobe Analytics 标记扩展迁移到 Web SDK 标记扩展](/help/implement/aep-edge/web-sdk/analytics-extension-to-web-sdk.md)以及[从 AppMeasurement 迁移到 Web SDK](../implement/aep-edge/web-sdk/appmeasurement-to-web-sdk.md)，以了解更多信息。 |  | 2024 年 4 月 |
| **仅限项目 [!UICONTROL 工作区] 组件的权限增强** | 以前，如果一个用户（用户 A）与另一个用户（用户 B）共享一个项目，并授予用户 B 编辑该项目的访问权限，则用户 B 将能够编辑该项目。但是，用户 B 无法编辑项目中嵌入的 [!UICONTROL 快速片段]。该限制现已取消 - 用户 B 可以编辑 [!UICONTROL 快速片段] 以及共享项目中嵌入的其他仅限项目的组件。 |  | 2024 年 4 月 17 日 |
| **对[!UICONTROL 数据馈送]、[!UICONTROL Data Warehouse] 和 [!UICONTROL 分类集]**&#x200B;使用相同的云帐户 | 您创建的云帐户和位置现在可用于导出数据（使用 [!UICONTROL 数据馈送] 和 [!UICONTROL Data Warehouse]）和导入数据（使用[!UICONTROL 分类集]）。<p> **配置帐户时的更改：** 用户可以 [配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/zh-hans/docs/analytics/components/locations/configure-import-accounts) 以及 [配置云导入和导出位置](https://experienceleague.adobe.com/zh-hans/zh-hans/docs/analytics/components/locations/configure-import-locations)，这些位置可用于以下任何目的：<ul><li>使用 [!UICONTROL 分类集导入数据]</li><li>使用 [!UICONTROL 数据馈送]导出数据</li><li>使用 [!UICONTROL Data Warehouse]导出数据。</li></ul><p>**从[!UICONTROL 位置]页面管理帐户和位置时的更改**：用户可以使用[位置](https://experienceleague.adobe.com/zh-hans/zh-hans/docs/analytics/components/locations/locations-manager)页面（在[!UICONTROL 组件] >“位置”下）查看和管理他们创建的所有帐户和位置，无论这些帐户和位置是在何处创建的。 <p>之前，[!UICONTROL 位置]页面仅适用于为导入带有[!UICONTROL 分类集]的数据而创建的帐户。</p>**从 [!UICONTROL Data Warehouse] 或[!UICONTROL 分类集]**&#x200B;管理位置时发生的变化<p>在管理给定应用程序区域（[!UICONTROL Data Warehouse] 或[!UICONTROL 分类集]）内的位置时，只有在该特定应用程序区域中创建的位置才可用。例如，查看 [!UICONTROL Data Warehouse] 应用程序区域时，只有 [!UICONTROL Data Warehouse] 位置可用。所有帐户在每个应用程序区域中仍然可用，无论它们是在哪个应用程序区域中创建的。以前，所有帐户和位置在每个应用程序区域中都可用，无论它们是在哪个应用程序区域中创建的。查看[!UICONTROL 数据馈送]应用程序区域时，情况仍然如此。 | | 2024 年 4 月 17 日 |
| **管理员可以管理其组织中的所有位置和帐户** | “位置”选项卡（在“组件”>“位置”页面）上的新选项允许管理员查看和管理组织中的所有位置。<p>[“位置”](https://experienceleague.adobe.com/zh-hans/zh-hans/docs/analytics/components/locations/locations-manager)帐户选项卡（在“组件”>“位置”页面）上的新选项允许管理员查看和管理组织中的所有帐户。</p> <p>以前，管理员只能查看和管理他们创建的位置和帐户。</p> |  | 2024 年 4 月 17 日 |
| **增大默认低流量阈值** | 在 **2024 年 4 月中旬**，Adobe 将开始增大默认报告包低流量阈值，如下所示：![低流量阈值](assets/thresholds.png) 这只会影响当前设置的小于新阈值的变量。这些更改将逐步进行，我们预计这项工作将在&#x200B;**五月底**&#x200B;之前完成。在实施这些增加时，您可能会注意到高基数变量的变化：<ul><li>更多维度值可用于报告。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报告包可能包含更多数据。</li><li>分类导出可能包含更多数据。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月 31 日 |
| **Activity Map 减少了 Web SDK 服务器调用次数** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。 <p>此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。</p> |  | 2024 年 5 月 31 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-343439；AN-343503；AN-343504；AN-343986；AN-344262；AN-344564；AN-345204；AN-345234
* 修复了以下分类规则生成器问题：AN-341488；AN-342501；AN-345751
* 修复了以下智能警报问题：AN-343466；
* 修复了以下分段问题：AN-342313
* 修复了以下 Data Warehouse 问题：AN-344292
* 修复了以下数据馈送问题：AN-339545；AN-340092；AN-342124；AN-342862；AN-343737；AN-344035；AN-344329；AN-344703；AN-344721；AN-344940；AN-345180；AN-345196；AN-345225；AN-345236；AN-345326；AN-345631；AN-345659
* 修复了以下数据源问题：AN-343541
* 修复了以下 Analysis Workspace 问题：AN-336303；AN-336472；AN-338422；AN-338556；AN-339718；AN-340147；AN-340301；AN-340421；AN-340951；AN-341172；AN-342905；AN-342909；AN-343448；AN-343570；AN-344050；AN-344182；AN-344763；AN-344768；
* 修复了以下分析管理员问题：AN-342519；AN-342523；AN-343623；AN-343882；AN-344237；AN-344829；AN-345235；
* 修复了以下 A4T 问题：AN-341619；AN-344402
* 修复了以下移动设备应用程序问题：AN-342010

### 其他 Analytics 修复

AN-336099；AN-337474；AN-337993；AN-339718；AN-339901；AN-340014；AN-341356；AN-343021；AN-343102；AN-343353；AN-343416；AN-340014；AN-344037；AN-344525；AN-345737

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

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2023 年发行说明](/help/release-notes/2023.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
