---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 39%

---

# 当前 Adobe Analytics 发行说明（2024 年 1 月）

**上次更新**：2024年1月10日

这些发行说明涵盖2024年1月至2024年2月13日的发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouse 更新** | Data Warehouse 现在有以下改进：<ul><li>在创建 Data Warehouse 请求时，用户现在可通过启用名为&#x200B;[!UICONTROL **提供给组织中的用户**]&#x200B;的新切换开关，将请求提供给组织中的所有用户。<p>有关详细信息，请参阅 [Data Warehouse 请求常规设置](/help/export/data-warehouse/create-request/dw-general-settings.md)。</p></li><li>在创建或管理 Data Warehouse 报告目标时，系统管理员现在可通过启用名为&#x200B;[!UICONTROL **显示所有目标**]&#x200B;的切换开关，显示组织中的用户创建的帐户和位置。<p>有关详细信息，请参阅[配置 Data Warehouse 请求的报告目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。</p></li> | 不适用 | 2024 年 1 月 10 日 |
| **关键量度摘要可视化图表的更新** | 在使用关键指标摘要可视化图表时，比较日期范围现在可以自动更新，具体取决于您选择的比较日期范围选项是相对于主日期范围还是相对于固定日期范围。 [了解详情](/help/analyze/analysis-workspace/visualizations/key-metric.md)。 | 不适用 | 2024年1月17日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-314821、AN-326839、AN-332079、AN-332704、AN-332812、AN-332902、AN-332975、AN-333300、AN-333023、AN-333033、AN-333174、AN-333910、AN-334097、AN-334208、AN-334373、AN-334439、AN-334698、AN-334838、AN-334848、AN-334987、AN-335046、AN-335082、AN-335202、AN-335203、AN-335254 an-335322； AN-335552； AN-335591； AN-335603； AN-335610； AN-335617； AN-335699； AN-335891； AN-335901； AN-336063； AN-336072； AN-336193； AN-336479； AN-336684； AN-336801； AN-337370； AN-337398； AN-； AN-； AN-； AN-； AN-； AN-； AN-
* 修复了以下分类规则生成器问题：AN-332390、AN-332573、AN-332718、AN-332927、AN-333248、AN-333953、AN-334647、AN-334736、AN-334910、AN-335642、AN-335683、AN-335811、AN-336033、AN-336569、AN-336852、AN-336875、AN-336902、AN-337190、AN-、AN-；
* 修复了以下A4T问题：AN-334564；AN-336178；
* 修复了以下服务器调用使用情况问题：AN-332568、AN-333105、AN-333167、AN-333983、AN-334209、AN-334278
* 修复了以下Data Warehouse问题：AN-333010、AN-333076、AN-330227、AN-331580、AN-333350、AN-334291、AN-334283、AN-334287、AN-334301、AN-334385、AN-334453、AN-334977、AN-335079、AN-335171、AN-335245、AN-335426、AN-335680、AN-335818、AN-336087、AN-337308、AN-、AN-、AN-。
* 修复了以下数据馈送问题：AN-332241、AN-332366、AN-332617、AN-332654、AN-332702、AN-332723、AN-333014、AN-333166、AN-334037、AN-334125、AN-334211、AN-334216、AN-334235、AN-334976、AN-335158、AN-335368、AN-335408、AN-335468、AN-335471、AN-335528、AN-335596、AN-335662、AN-335733、AN-335883 AN-335894； AN-335968； AN-336098； AN-336192； AN-336243； AN-336659； AN-336977； AN-337117； AN-337219； AN-337262； AN-337393； AN-337462； AN-337854； AN-； AN-
* 修复了以下Report Builder问题：AN-335246；AN-336311；
* 修复了以下Analysis Workspace问题：AN-323760、AN-324191、AN-324913、AN-330126、AN-332808、AN-333168、AN-333382、AN-334839、AN-336040、AN-337043；

### 其他修复

AN-323975、AN-325383、AN-325809、AN-326787、AN-331611、AN-331818、AN-332124、AN-332272、AN-332911、AN-333070、AN-333302、AN-333377、AN-333904、AN-333928、AN-333968、AN-334056、AN-334099、AN-334191、AN-334207、AN-334776、AN-335206、AN-335294、AN-335320、AN-335394、AN-335443、AN-335967 -336099； AN-337452； AN-337463

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 添加API对象成员Adobe | 2024年1月17日 | Adobe可以将可选请求和响应成员（名称/值对）添加到现有API对象，而无需在版本控制中通知或更改。 此类添加内容应该对您的实施进行不间断的更改。 Adobe建议您查阅与我们的API集成的任何第三方工具的API文档，以便在处理过程中忽略不了解的此类添加。 如果未首先通过发行说明提供标准通知，Adobe将不会移除参数或添加所需参数。 |
| `getPageLoadTime` 插件已弃用 | 2024 年 1 月 10 日 | 不再支持此插件。 其代码使用performance.timing方法，该方法（根据MDN）已 [已弃用](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). 已启动更新插件的工作。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** 的 EOL | 2024 年 1 月 10 日 | 有效 **2024年1月17日**，已停止Adobe [!DNL Reports & Analytics] 及其随附的报告和功能。 支持的报表、可视化图表和底层技术 [!DNL Reports & Analytics] 不再满足Adobe的技术标准。 大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2024年1月17日，我们终止了多项与Reports &amp; Analytics相关的功能，其中包括但不限于：计划报表、数据提取和DL报表。 2024年1月17日之后，不再发送任何计划报告。 此外，从2024年1月17日起，您无法再计划未来报表。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2024 年 1 月 10 日 | 作为Reports &amp; Analytics EOL的一部分， [!UICONTROL 发布列表] 生命周期结束日期 **2024年1月17日**. 您无法再创建新或访问现有 [!UICONTROL 发布列表] 发送或计划 [!UICONTROL Analysis Workspace] 项目。 |
| **结束 Data Workbench 的生命周期** | 2024 年 1 月 2 日 | Adobe 在 **2023 年 12 月 31 日**&#x200B;结束了 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://express.adobe.com/page/GSu6oKOD88GAj/)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.25.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2023 年发行说明](/help/release-notes/2023.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
