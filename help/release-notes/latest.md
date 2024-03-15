---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7cb7953e3321f2e8fa814ef6f1607cbe8d0f44de
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 46%

---

# 当前的 Adobe Analytics 发行说明（2024 年 3 月）

**上次更新**：2024年3月13日

这些发行说明涵盖2024年3月12日至2024年4月的发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurement 更新** | [AppMeasurement 版本 v2.26.0](/help/implement/appmeasurement-updates.md) 现已推出。 | | 2024 年 3 月 4 日 |
| **项目登陆页上提供的新列** | 此 **[!UICONTROL 上次使用时间]** 列现在可用于查看上的项目选项卡 [Adobe Analytics登录页面](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=zh-Hans). <p>此信息可以显示上次打开项目的日期和时间，从而帮助您确定项目对组织中的用户是否有价值。</p> <p>以前， **[!UICONTROL 上次使用时间]** 列仅在计算量度管理器、区段管理器和警报管理器中可用。</p> |  | 2024 年 3 月 13 日 |
| **Analytics支持Google所需的DMA同意标记** | 由于新的欧洲隐私法规，Google要求在欧洲收集的数据必须表明是否授予了两种特定类型的同意。 **从3月6日开始**，Google将不再接受未表明已授予相关同意的事件数据。 Adobe Analytics已发布支持功能，允许通过新的adConsent变量捕获此数据。 您可以在中看到新变量列出 [隐私报表UI](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). 如果要激活此项，并且已为以前的同意变量启用隐私，则需要重新启用隐私。 |  | 2024 年 3 月 13 日 |
| **将相同的云帐户用于数据馈送、Data Warehouse和分类集** | 您创建的云帐户和位置现在可用于导出数据(使用数据馈送和Data Warehouse)和导入数据（使用分类集）。<p> **配置帐户时的更改：** 用户可以配置云导入和导出帐户以及配置可用于以下任意目的的云导入和导出位置：<ul><li>使用分类集导入数据</li><li>使用数据馈送导出数据</li><li>使用Data Warehouse导出数据。</li></ul><p>**管理帐户时的更改**：用户可以使用“位置”页面（在“组件”>“位置”下）查看和管理其创建的所有帐户和位置，而不管这些帐户和位置是在何处创建的。 <p>以前，“位置”页面仅适用于为导入具有分类集的数据而创建的帐户。</p> | | 2024 年 4 月 |
| **管理员可以管理其组织中的所有位置** | “位置”页面上的新选项允许管理员查看和管理组织中的所有位置。 <p>以前，管理员只能查看和管理他们创建的位置。</p> |  | 2024 年 4 月 |
| **Activity Map对Web SDK使用的服务器调用较少** | 目前，Activity Map链接事件会计为自己的事件，并产生额外费用。 <p>此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。</p> |  | 2024 年 4 月 3 日 |
| **增大默认低流量阈值** | 在 **2024 年 4 月中旬**，Adobe 将开始增大默认报表包低流量阈值，如下所示：![低流量阈值](assets/thresholds.png) 这只会影响当前设置的小于新阈值的变量。这些更改将逐步进行，我们预计这项工作将在&#x200B;**五月底**&#x200B;之前完成。在实施这些增加时，您可能会注意到高基数变量的变化：<ul><li>更多维度值可用于报告。</li><li>区段和计算量度可能包含更多数据。</li><li>基于区段的虚拟报表包可能包含更多数据。</li><li>分类导出可能包含更多数据。</li></ul> | | 2024 年 4 月中旬 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-335632、AN-337559、AN-340164、AN-340370、AN-341089、AN-341211、AN-341284、AN-341469、AN-341481、AN-341760、AN-341778、AN-342144、AN-342258、AN-342338、AN-342400、AN-
* 修复了以下分类规则生成器问题：AN-340921、AN-341269、AN-341292、AN-341467、AN-341666、AN-342145、AN-342329
* 修复了以下智能警报问题：AN-340736
* 修复了以下分段问题：AN-336242
* 修复了以下Data Warehouse问题：AN-335354、AN-339446、AN-339774、AN-340221、AN-340599、AN-341277、AN-342009、AN-342088、AN-342592
* 修复了以下数据馈送问题：AN-335508、AN-340887、AN-341050、AN-341208、AN-341403、AN-341479、AN-341524、AN-341661、AN-342000、AN-342125、AN-342256、AN-342301、AN-342410、AN-342502、AN-342525、AN-
* 修复了以下Report Builder问题：AN-340540
* 修复了以下Analysis Workspace问题：AN-295889、AN-330981、AN-338818、AN-339730、AN-341114、AN-341520；

### 其他 Analytics 修复

AN-312198、AN-338009、AN-339549、AN-333970、AN-334790、AN-336461、AN-336572、AN-339549、AN-341119、AN-341246、AN-341268、AN-341272、AN-341475、AN-341547、AN-341558、AN-341680、AN-342017；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **添加API对象成员Adobe** | 2024 年 1 月 17 日 | Adobe 可能会随时无通知或在版本控制中无变更地将可选的请求和响应成员（名称/值对）添加到现有的 API 对象。Adobe 建议您参考与我们的 API 集成的任何第三方工具的 API 文档，以便在处理过程中忽略不了解的此类添加。如果正确实施，则此类添加应为不令您的实施发生中断的更改。如果没有首先通过发行说明提供标准通知，Adobe 不会删除参数或添加所需参数。 |
| **`getPageLoadTime`插件已弃用** | 2024 年 1 月 10 日 | 不再支持此插件。其代码利用了 performance.timing 方法，而（据 MDN 称）该方法已被[弃用](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)。更新插件的工作已经开始。 |

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
