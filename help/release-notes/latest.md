---
title: 当前 Adobe Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5d0133495613c89deca4dc070d38389ef89853b3
workflow-type: ht
source-wordcount: '891'
ht-degree: 100%

---

# 当前 Adobe Analytics 发行说明（2023 年 8 月）

**上次更新日期**：2023 年 8 月 24 日

这些发行说明涵盖 2023 年 8 月 9 日至 9 月 13 日的发行期。Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **API 2.0 中的分类集** | 提供用于保存、删除、检索、导入和导出分类集数据的 Adobe Analytics API 2.0 方法。 | 不适用 | 2023 年 8 月 30 日 |
| **报表活动管理器** | 报告活动管理器使管理员能够详细看到每个报告包的报告消耗情况的详细信息，使管&#x200B;&#x200B;理员能够轻松诊断并修复报告高峰期间的容量问题。[了解详情](/help/admin/admin/reporting-activity.md) | 不适用 | 2023 年 9 月 12 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了自定义事件未加载的问题。(AN-324163)
* 修复了无法编辑可视化中图例标签的问题。(AN-323246)

AN-315605、AN-316306、AN-317494、AN-317844、AN-320424、AN-320597、AN-320680、AN-320869、AN-321624、AN-321693、AN-322009、AN-322244、AN-322380、AN-322432、AN-322466、AN-322556、AN-322669、AN-322735、AN-323151、AN-323220、AN-323380、AN-323492、AN-323595、AN-323755、AN-323854、AN-323916、AN-324044、AN-324200、AN-324213、AN-324238、AN-324347、AN-323598、AN-323625、AN-323631、AN-323638、AN-323641、AN-323755、AN-323767、AN-323777、AN-323825、AN-323846、AN-323972、AN-324113、AN-324170、AN-324197、AN-324273、AN-324275、AN-324345、AN-324384、AN-324433、AN-324511、AN-324513、AN-324521、AN-324524、AN-324531、AN-324532、AN-324534、AN-324537、AN-324569、AN-324618、AN-324635、AN-324688、AN-324704、AN-324712、AN-324721、AN-324745、AN-324792、AN-324793、AN-324794、AN-324795、AN-324824、AN-324905、AN-324918、AN-324932、AN-324934、AN-324947、AN-325003、AN-325073、AN-325143、AN-325148、AN-325153、AN-325177、AN-325187、AN-325252、AN-325305、AN-325363、AN-325401、AN-325439、AN-325431、AN-325491、AN-325495、AN-325508、AN-325594、AN-325601、AN-325660、AN-325779、AN-325857、AN-325883、AN-325885、AN-325886


## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **购买 ID 和事件 ID（事件序列化）在 37 个月后到期** | 2023 年 7 月 10 日 | **2023 年 7 月 13 日**&#x200B;发行的 Analytics Hit 处理引擎的最新版本，已开始强制购买 ID 和事件 ID（事件序列化）在 37 个月后到期。购买 ID 和事件 ID 以前在 Adobe Analytics 中永不到期。一旦查看/使用购买 ID 或事件 ID，以后无论何时的任何点击都将该购买或事件标为重复。在新的处理引擎发布后：<ul><li>购买 ID 和事件 ID 始终在 37 个月后到期。</li><li>如果自查看购买 ID 或事件 ID 以来已有 37 个月，则不再将它视为重复的购买或事件。</li><li> 如果正在“重用”大于 37 个月之前的购买 ID 或事件 ID，则不再将其视为重复。</li></ul> |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。有关更多详细信息和时间表，请参阅下表中的终止使用通知。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。在 **2023 年 4 月**，任何计划在 2023 年 12 月 31 日之后到期的报告将会自动更新并恢复到 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports &amp; Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用[!UICONTROL 发布列表]。您将无法创建新的[!UICONTROL 发布列表]或访问现有的发布列表以发送或安排 [!UICONTROL Analysis Workspace] 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.24.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
