---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 98890c72a375b61bcecb79f2d32b3f29ee5782bd
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 64%

---

# 当前 Adobe Analytics 发行说明 (2023 年 2 月)

**上次更新时间**：2023 年 2 月 15 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## Adobe Analytics 的新增或更新功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新了数据隐私标签的用户界面** | 更新的界面简化了报表包组件创建、管理和编辑数据隐私标签的过程。 [了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | 不适用 | 2023 年 2 月 8 日 |
| **在移动记分卡中隐藏比较日期范围** | 通过移动记分卡，您可以 **[!UICONTROL 包括比较日期]** 设置以查看或隐藏比较日期。 | 不适用 | 2023 年 2 月 8 日 |
| **Workspace 中的日程表更新** | <ul><li>锚定面板日期：您可以使日期范围组件与面板日历相对的选项。[了解详情](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>日程表样式更新：整个 UI 中的日程表样式已升级，以呈现更加一致且易于使用的工作流程。</li><li>日程表公式更新：如果您使用相对日期，所有的日程表公式都会反映面板日期范围的开始。[了解详情](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | 不适用 | 2023 年 2 月 8 日 |
| **Adobe Analytics 源连接器流的行/列筛选** | Adobe Experience Platform 中的 Analytics 源连接器现在允许过滤 Analytics 数据，这些数据用于填充[实时客户配置文件](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en)中的配置文件。行级过滤有助于减少与配置文件关联的事件数。列级别过滤有助于减少事件本身的丰富性，从而使您能够优化用户档案权利的使用。 此过滤仅适用于发送至实时客户配置文件和[标识服务](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en)的数据。**过滤不会影响发送到数据湖以用于 Customer Journey Analytics** 等应用程序的数据。[了解详情](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | 不适用 | 2023 年 2 月 22 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

-302282、AN-303127、AN-303541、AN-303550、AN-305282、AN-306504、AN-307351、AN-307496、AN-307530、AN-307947、AN-308497、AN-、AN-308610、AN-308777、AN-308994、AN-309143、AN-309404、AN-309414、AN-309445、AN-309575、AN-309630、AN-309658、AN-309690、AN-309742、AN-309861、AN-309967、AN-309973、AN-310059、AN-310132、AN-310168、AN-310238、AN-310241、AN-310301、AN-310318、AN-310324、AN-310335、AN-310338、AN-310460、AN-310500、AN-310684、AN-310690、AN-311010、AN-311022、AN-311043、AN-311125、AN-311250、AN-311370、AN-311458；

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **Analytics源连接器可用性** | 2023 年 2 月 15 日 | 2023年2月28日，将在位于加拿大的新Adobe Experience Platform数据中心提供Analytics源连接器。 |
| **自动迁移到分类集架构** | 2023 年 2 月 8 日 | 在接下来的几个月中，Adobe计划将所有组织中的所有分类迁移到最新的分类架构。 据估计，最后一个要迁移的客户将于2023年5月完成。 无需客户操作，也无需停机。 此新架构具有许多好处，包括：<ul><li>显着缩短了处理时间(72小时→24小时)</li><li>使用 [分类集](/help/components/classifications/sets/overview.md) UI</li><li>将来可通过使用 [Adobe Analytics源连接器用于分类数据](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>请注意以下可能影响贵组织工作流程的更改：<ul><li>使用浏览器或FTP导入时，&#39;[!UICONTROL 冲突时覆盖]始终启用“ ”。</li><li>使用浏览器或FTP导入时，不再支持导入后立即导出的选项。</li><li>Analytics 2.0 API `GetDimensions` 端点现在会返回分类的字符串标识符，而不是数字标识符。 数字标识符仍可以使用，但Adobe建议尽可能使用新的字符串标识符。 数字标识符可使用 `?expansion=hidden` 查询字符串参数。</li></ul>如果您希望为贵组织制定更具体的迁移计划，或者对此迁移存有疑问/疑虑，请联系Adobe客户关怀团队。 [了解详情](/help/components/classifications/sets/overview.md) |
| **由于 Google 客户端提示而更新设备查找** | 2023 年 1 月 25 日 | 在设备查找中使用客户端提示的功能将于 **2023 年 2 月 16 日**&#x200B;开始可用。 <p> <p>自 2022 年 10 月起，可以使用 Web SDK 或 AppMeasurement JavaScript 库收集客户端提示。但直到 2023 年 2 月才将客户端提示纳入设备查找。届时，在为来自 Chromium 浏览器（如 Google Chrome 和 Microsoft Edge）的点击派生某些设备信息时，Adobe 除了使用用户代理程序之外，还将开始使用客户端提示。这是为了响应 Google 的计划，该计划逐步减少从 User-Agent 字符串产生的信息，并用通过客户端提示传递的数据替代。 <p> <p>作为此更改的一部分，Adobe 将使用 Device Atlas 执行所有与 User-Agent 相关的设备查找。[了解详情](/help/technotes/client-hints.md) |

{style=&quot;table-layout:auto&quot;}

## 终止生命周期(EOL)通知

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **某些Reports &amp; Analytics和Report Builder计划功能生命周期终止** | 2023 年 2 月 9 日 | 2023年1月31日终止提供以下计划功能：<ul><li>“发生x次后结束”选项，用于每小时任务Report Builder</li><li>在Reports and Analytics中计划新报表和下载数据提取的功能</li></ul><p>**注意**:我们最初于2022年4月终止了这些功能，但回滚了更改。 我们还发送了一则通知，说这些功能正在临时恢复，并将于2023年1月31日重新终止。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports and Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用发布列表。您将无法创建新的发布列表或访问现有的发布列表以发送或安排 Analysis Workspace 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html)以了解详情。如有任何问题，请与您组织的 Adobe 客户经理联系。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
