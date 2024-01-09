---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: baac0c0384b714cf2ca536149ca10eec3a7065ad
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 87%

---

# 当前Adobe Analytics发行说明（2024年1月）

**上次更新**：2024年1月8日

这些发行说明涵盖2024年1月发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouse更新** | 现已提供以下Data Warehouse改进：<ul><li>创建Data Warehouse请求时，用户现在可以通过启用新的切换功能(称为 [!UICONTROL **对贵组织中的用户可用**].<p>有关更多信息，请参阅 [Data Warehouse请求常规设置](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>创建或管理Data Warehouse报表目标时，系统管理员现在可以通过启用名为的切换来显示组织中用户创建的帐户和位置 [!UICONTROL **显示所有目标**].<p>有关更多信息，请参阅 [为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | 不适用 | 2024年1月10日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 将在 10 月的最后一周部署这些对分析处理和报告引擎的更改：我们将修复一个问题，在该问题中错误地将页面或链接维度的标签显示为 `Unknown`。在修复之前，当在点击后未传入页面名称或链接名称（默认值分别为[!UICONTROL 页面 URL] 和[!UICONTROL 链接 URL]）时，可能已错误地显示 `Unknown` 标签。已将这些维度配置为不区分大小写。通过此修复，以后的报告将正确无误。但是对于涉及历史数据的报告，某些报告结果可能仍被错误地称为 `Unknown`。(AN-328030)

### 其他修复

AN-315676；AN-323398；AN-326209；AN-328178；AN-328261；AN-328395；AN-328671；AN-329282；AN-329330；AN-329355；AN-329506；AN-329516；AN-329738；AN-329769；AN-329771；AN-329816；AN-329877；AN-329928；AN-329957；AN-329962；AN-329966；AN-330023；AN-330081；AN-330083；AN-330105；AN-330138；AN-330140；AN-330165；AN-330241；AN-330359；AN-330366；AN-330427；AN-330438；AN-330442；AN-330534；AN-330616；AN-330654；AN-330783；AN-330879；AN-330881；AN-330883；AN-330887；AN-330888；AN-330955；AN-330979；AN-331031；AN-331053；AN-331068；AN-331071；AN-331074；AN-331075；AN-331076；AN-331078；AN-331085；AN-331093；AN-331167；AN-331171；AN-331181；AN-331196；AN-331226；AN-331258；AN-331260；AN-331279；AN-331286；AN-331290；AN-331365；AN-331375；AN-331376；AN-331454；AN-331519；AN-331570；AN-331590；AN-331593；AN-331603；AN-331751；AN-331816；AN-331897；AN-331900；AN-331906；AN-331926；AN-331929；AN-332031；AN-332067；AN-332101；AN-332114；AN-332156；AN-332201；AN-332225；AN-332253；AN-332277；AN-332361；AN-332370；AN-332386

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **Adobe Experience Edge 命中的完整 IP 模糊处理** | 2023 年 9 月 27 日 | 将在 2023 年 10 月晚些时候更新对于 Experience Edge 产生的点击模糊处理 IP 地址。2023 年 4 月，Experience Edge 添加了模糊处理 IP 地址的功能。那时，由于 Analytics 处理来自 Experience Edge 的命中的方式，Adobe Analytics 仅支持对 IP 进行部分模糊处理。当客户为 Experience Edge 选择完全模糊处理时，Analytics 仅收到已部分模糊处理的 IP。实施此更改后，Analytics 将收到已完全模糊处理的 IP。 |
| **Adobe Analytics Livestream - Analytics 2.0 API** | 2023 年 9 月 27 日 | 客户现在可以在 Adobe Analytics 2.0 API 下，而不是在其之前的位置（即 1.4 API）访问 [Adobe Analytics Livestream 端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/)。请注意，使用 Adobe I/O JWT 凭据的客户必须在 2025 年 1 月 1 日之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。（请参阅下面的 EOL 通知下的详细信息。） |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 12 月 13 日 | 自 **2024 年 1 月 17 日**&#x200B;起，Adobe 决定不再提供 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。**2023 年 4 月**&#x200B;自动更新了任何以前安排在 2023 年 12 月 31 日之后到期的报告，并将其恢复为 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2023 年 12 月 13 日 | 作为终止使用 Reports &amp; Analytics 的一部分，预计 **2024 年 1 月 17 日**&#x200B;终止使用[!UICONTROL 发布列表]。您将无法创建新的或访问现有的[!UICONTROL 发布列表]以发送或安排 [!UICONTROL Analysis Workspace] 项目。 |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Data Workbench 的生命周期结束日期** | 2024年1月2日 | Adobe生命周期结束Data Workbench有效 **2023年12月31日**. 请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.25.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
