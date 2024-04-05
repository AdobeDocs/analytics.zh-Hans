---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: aac32bdda365ce4534f1d4c04e816eb6f03b991c
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 97%

---

# 当前的 Adobe Analytics 发行说明（2024 年 3 月）

**上次更新时间**：2024 年 4 月 3 日

这些发行说明涵盖 2024 年 3 月 12 日至 2024 年 4 月的发行期。Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更改 Workspace 项目的删除协议** | 以前，从未从系统中清除已删除的项目。 现在，我们会在 180 天后开始清除已删除的项目。删除后的180天内，如果用户拥有已删除项目的URL，则仍可以通过Web界面访问这些项目。 | | 2024 年 3 月 14 日 |
| **AppMeasurement 更新** | [AppMeasurement 版本 v2.26.0](/help/implement/appmeasurement-updates.md) 现已推出。 | | 2024 年 3 月 4 日 |
| **项目登陆页面上提供了新专栏** | 现在，在查看 [Adobe Analytics 登录页面](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=zh-Hans)上的“项目”选项卡时，可以使用&#x200B;**[!UICONTROL 上次使用的]**&#x200B;列。 <p>此信息可以通过显示项目上次打开的日期和时间来帮助您确定项目对组织中的用户是否有价值。</p> <p>以前，**[!UICONTROL 上次使用]**&#x200B;列仅在计算量度管理器、分段管理器和警报管理器中可用。</p> |  | 2024 年 3 月 13 日 |
| **对 Google for DMA 所需的同意标记的分析支持** | 根据新的欧洲隐私法规，Google 要求在欧洲收集并发送给他们的数据必须注明是否获得了两种特定的同意。 **从 3 月 6 日开始**，Google 将不再接受未注明已获得相关同意的事件数据。Adobe Analytics 已发布支持通过新的 adConsent 变量捕获这些数据。您可以在[隐私报告 UI](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) 中查看列出的新变量。如果您想激活此功能，但之前的同意变量已经启用了隐私功能，则需要再次启用隐私功能。<p>[“广告平台同意书”维度](/help/components/dimensions/ad-consent.md)显示是否已收集的同意书，以将数据发送给第三方广告提供商（例如 Google）。 |  | 2024 年 3 月 13 日 |
| **Report Builder 的使用情况包含在计算量度管理器和区段管理器的“用于”列中** | 在计算量度管理器或区段管理器中查看“**用于**”列时，Report Builder 现在可提供使用情况数据。<p>以前，区段管理器中的使用情况数据仅适用于警报、项目、已计划项目和计算量度；而计算量度管理器中的使用情况数据仅适用于警报、项目和已计划项目。</p> |  | 7 月 |
| **对数据馈送、Data Warehouse 和分类集使用相同的云帐户** | 您创建的云帐户和位置现在可用于导出数据（使用数据馈送和 Data Warehouse）和导入数据（使用分类集）。<p> **配置帐户时的更改：** 用户可以配置云导入和导出帐户以及配置云导入和导出位置，这些位置可用于以下任何目的：<ul><li>使用分类集导入数据</li><li>使用数据馈送导出数据</li><li>使用 Data Warehouse 导出数据。</li></ul><p>**管理帐户时的更改**：用户可以使用“位置”页面（在“组件”>“位置”下）查看和管理他们创建的所有帐户和位置，无论这些帐户和位置是在何处创建的。 <p>之前，“位置”页面仅适用于为导入带有分类集的数据而创建的帐户。</p> | | 2024 年 4 月 |
| **管理员可以管理其组织中的所有位置和帐户** | “位置”选项卡（在“组件”>“位置”页面）上的新选项允许管理员查看和管理组织中的所有位置。<p>“位置”帐户选项卡（在“组件”>“位置”页面）上的新选项允许管理员查看和管理组织中的所有帐户。</p> <p>以前，管理员只能查看和管理他们创建的位置和帐户。</p> |  | 2024 年 4 月 |
| **Activity Map 减少了 Web SDK 服务器调用次数** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。 <p>此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。</p> |  | 2024 年 4 月 31 日 |
| **增大默认低流量阈值** | 在 **2024 年 4 月中旬**，Adobe 将开始增大默认报告包低流量阈值，如下所示：![低流量阈值](assets/thresholds.png) 这只会影响当前设置的小于新阈值的变量。这些更改将逐步进行，我们预计这项工作将在&#x200B;**五月底**&#x200B;之前完成。在实施这些增加时，您可能会注意到高基数变量的变化：<ul><li>更多维度值可用于报告。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报告包可能包含更多数据。</li><li>分类导出可能包含更多数据。</li></ul> | | 2024 年 4 月中旬 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-335632; AN-337559；AN-340164；AN-340370；AN-341089；AN-341211；AN-341284；AN-341469；AN-341481；AN-341760；AN-341778；AN-342144；AN-342258；AN-342338；AN-342400；
* 修复了以下分类规则生成器问题：AN-340921；AN-341269；AN-341292；AN-341467；AN-341666；AN-342145；AN-342329
* 修复了以下智能警报问题：AN-340736
* 修复了以下分段问题：AN-336242
* 修复了以下 Data Warehouse 问题：AN-335354；AN-339446；AN-339774；AN-340221；AN-340599；AN-341277；AN-342009；AN-342088；AN-342592
* 修复了以下数据馈送问题：AN-335508; AN-340887；AN-341050；AN-341208；AN-341403；AN-341479；AN-341524；AN-341661；AN-342000；AN-342125；AN-342256；AN-342301；AN-342410；AN-342502；AN-342525；
* 修复了以下 Report Builder 问题：AN-340540
* 修复了以下 Analysis Workspace 的问题：AN-295889；AN-330981；AN-338818；AN-339730；AN-341114；AN-341520；

### 其他 Analytics 修复

AN-312198；AN-338009；AN-339549；AN-333970；AN-334790；AN-336461；AN-336572；AN-339549；AN-341119；AN-341246；AN-341268；AN-341272；AN-341475；AN-341547；AN-341558；AN-341680；AN-342017

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **保存的`cust_visids`** 13 个月有效期 | 2024 年 3 月 20 日 | 即将发布的 Analytics Hit 处理引擎（预计于 4 月或 5 月发布）将开始对保存的 `cust_visids` 强制执行 13 个月的有效期。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。目前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期。在此版本中，如果自 `visid_high/visid_low` 点击 `cust_visid` 以来已经过去了 13 个月或更长时间，则映射将会过期。 |
| **添加了 Adobe API 对象成员** | 2024 年 1 月 17 日 | Adobe 可能会随时无通知或在版本控制中无变更地将可选的请求和响应成员（名称/值对）添加到现有的 API 对象。Adobe 建议您参考与我们的 API 集成的任何第三方工具的 API 文档，以便在处理过程中忽略不了解的此类添加。如果正确实施，则此类添加应为不令您的实施发生中断的更改。如果没有首先通过发行说明提供标准通知，Adobe 不会删除参数或添加所需参数。 |
| **`getPageLoadTime`插件被弃用** | 2024 年 1 月 10 日 | 不再支持此插件。其代码利用了 performance.timing 方法，而（据 MDN 称）该方法已被[弃用](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)。更新插件的工作已经开始。 |

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
