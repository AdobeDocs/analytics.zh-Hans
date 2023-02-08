---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e7140b78b7b2c6c63cb93f1341581cc83af7b33b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 当前 Adobe Analytics 发行说明 (2023 年 2 月)

**上次更新时间**：2023 年 2 月 2 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## Adobe Analytics 的新增或更新功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新了数据隐私标签的用户界面** | 更新的界面简化了报表包组件创建、管理和编辑数据隐私标签的过程。 [了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | 不适用 | 2023年2月8日 |
| **移动记分卡中的比较日期范围** | 通过移动记分卡，您可以 **[!UICONTROL 包括比较日期]** 设置以查看或隐藏比较日期。 | 不适用/ | 2023年2月8日 |
| **工作区中的日历更新** | <ul><li>锚点面板日期：您可以使日期范围组件相对于面板日历。 [了解详情](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>日历样式更新：整个UI中的日历样式都已升级，可提供更一致、更易于使用的工作流。</li><li>日历公式更新：如果使用相对日期，则所有日历公式都将反映面板日期范围的开始日期。 [了解详情](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | 不适用 | 2023年2月8日 |
| **Adobe Analytics源连接器流的行/列过滤** | Adobe Experience Platform中的Analytics源连接器现在允许过滤用于填充 [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans). 行级过滤有助于减少与用户档案关联的事件数。 列级别过滤有助于减少事件本身的丰富性，从而使您能够优化用户档案权利的使用。 此过滤仅适用于发送到实时客户资料和 [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hans). **过滤不会影响发送到数据湖以用于应用程序(如Customer Journey Analytics)的数据**. [了解详情](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | 不适用 | 2023 年 2 月 22 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

-302282、AN-303127、AN-303541、AN-303550、AN-305282、AN-306504、AN-307351、AN-307496、AN-307530、AN-307947、AN-308497、AN-、AN-308610、AN-308777、AN-308994、AN-309143、AN-309404、AN-309414、AN-309445、AN-309575、AN-309630、AN-309658、AN-309690、AN-309742、AN-309861、AN-309967、AN-309973、AN-310059、AN-310132、AN-310168、AN-310238、AN-310241、AN-310301、AN-310318、AN-310324、AN-310335、AN-310338、AN-310460、AN-310500、AN-310684、AN-310690、AN-311010、AN-311022、AN-311043、AN-311125、AN-311250、AN-311370、AN-311458；

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **由于 Google 客户端提示而更新设备查找** | 2023 年 1 月 25 日 | 在设备查找中使用客户端提示的功能将于 **2023 年 2 月 16 日**&#x200B;开始可用。 <p> <p>自 2022 年 10 月起，可以使用 Web SDK 或 AppMeasurement JavaScript 库收集客户端提示。但直到 2023 年 2 月才将客户端提示纳入设备查找。届时，在为来自 Chromium 浏览器（如 Google Chrome 和 Microsoft Edge）的点击派生某些设备信息时，Adobe 除了使用用户代理程序之外，还将开始使用客户端提示。这是为了响应 Google 的计划，该计划逐步减少从 User-Agent 字符串产生的信息，并用通过客户端提示传递的数据替代。 <p> <p>作为此更改的一部分，Adobe 将使用 Device Atlas 执行所有与 User-Agent 相关的设备查找。[了解详情](/help/technotes/client-hints.md) |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2023 年 1 月 6 日 | Adobe在 **2023年1月31日**. 请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>在2023年1月31日之前，您必须将计划报表迁移到Adobe Analytics中可用的其他机制之一。 如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2023 年 1 月 6 日 | 开 **2023年1月31日**,Adobe在Report Builder中对计划任务进行了更改，以此作为性能和交付优化工作的一部分。 这些更改包括取消预定交付“在发生 x 次后结束”的功能。<p>您可以继续计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生 x 次后结束”不可用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## 生命周期终止通知

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html)以了解详情。如有任何问题，请与您组织的 Adobe 客户经理联系。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports and Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用发布列表。您将无法创建新的发布列表或访问现有的发布列表以发送或安排 Analysis Workspace 项目。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
