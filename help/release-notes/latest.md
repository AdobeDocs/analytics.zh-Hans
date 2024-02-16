---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d52e4d41ac0fc6ce6db04e491fc33bac2284f040
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 42%

---

# 当前的 Adobe Analytics 发行说明（2024 年 2 月）

**上次更新**：2024年2月16日

这些发行说明涵盖2024年2月14日至2024年3月11日的发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Activity MapWeb SDK，无需额外付费** | 目前，Activity Map链接事件会计为自己的事件，并产生额外费用。 此增强功能采用一些链接事件并将它们打包到下一次点击中，这与AppMeasurement处理事件的方式类似。 |  | 2024年3月6日 |
| **提高默认低流量阈值** | 在 **2024年4月中**，Adobe将开始增加默认报表包的低流量阈值，如下所示： ![低流量阈值](assets/thresholds.png) 这将仅影响当前设置低于新阈值的变量。 这些更改将以增量方式进行，我们预计工作将在 **5月底**. 在推出这些增加时，您可能会注意到高基数变量的更改：<ul><li>可能有更多维度值可用于报表。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报表包可能包含更多数据。</li></ul> | 2024年4月中旬 | 2024年5月底 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-319515、AN-337559、AN-338149、AN-338702、AN-338769、AN-338891、AN-339327、AN-339649、AN-339668、AN-339669、AN-339776、AN-339822、AN-340017、AN-340202、AN-340476；
* 修复了以下分类规则生成器问题：AN-338385、AN-338399、AN-338592、AN-338810、AN-338893、AN-339431、AN-339894、AN-339933、AN-340201、AN-340309；
* 修复了以下A4T问题：AN-334830；AN-336194；AN-338309；AN-338650；
* 修复了以下数据收集问题：AN-339323
* 修复了以下Data Warehouse问题：AN-335542、AN-331425、AN-337215、AN-338445、AN-338643、AN-338651、AN-339461、AN-340066、AN-340207、AN-340460
* 修复了以下数据馈送问题：AN-335952、AN-338653、AN-339508、AN-339681、AN-340418
* 修复了以下数据源问题：AN-338648
* 修复了以下Analysis Workspace问题：AN-326509、AN-336186、AN-336190、AN-336309、AN-337922、AN-338094、AN-338323、AN-338556、AN-339600、AN-340445

### 其他 Analytics 修复

AN-328239、AN-332908、AN-335449、AN-335517、AN-336075、AN-336100、AN-336128、AN-338088、AN-338270、AN-338393、AN-338494、AN-339326、AN-339742、AN-339883、AN-340419；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 添加了 Adobe API 对象成员 | 2024 年 1 月 17 日 | Adobe可随时向现有API对象添加可选请求和响应成员（名称/值对），而无需通知或更改版本控制。 Adobe建议您参阅与我们的API集成的任何第三方工具的API文档，以便在处理过程中忽略此类添加（如果无法理解）。 如果实施正确，此类添加内容将对您的实施产生不间断的更改。 如果没有首先通过发行说明提供标准通知，Adobe 不会删除参数或添加所需参数。 |
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
