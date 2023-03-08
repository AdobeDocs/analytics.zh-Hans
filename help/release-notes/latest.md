---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6e6fcca0c2fa1fd1ee433c7d1b9727c058bb711e
workflow-type: tm+mt
source-wordcount: '1062'
ht-degree: 58%

---

# 当前 Adobe Analytics 发行说明 (2023 年 3 月)

**上次更新日期**：2023 年 3 月 7 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## Adobe Analytics 的新增或更新功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace中的数据字典** | 数据字典可帮助用户和管理员跟踪、管理和更好地了解其Analytics环境中的组件（维度、量度）。 [了解详情](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023年3月15日 | 2023年3月22日 |
| **移动仪表板中的数据故事** | 通过数据故事，可将多个可自定义的详细信息视图添加到移动记分卡项目中的图块。 使用数据故事在客户历程中更深入地探讨关键驱动因素、相关指标和不同步骤。 您可以轻松地浏览这些视图，以了解关键量度背后的整个故事。 [了解详情](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | 不适用 | 2023年3月8日 |
| **计划项目的到期日期** | 您可以将计划项目的最长到期日期设置为一年，而不管计划频率如何。 | 不适用 | 2023年3月8日 |
| **项目链接共享（无需登录）**  — 仅私人测试版访问 | <p>您现在可以与无权访问Analysis Workspace的用户共享Adobe Analytics项目的只读链接。 您可以与组织外部的人员或组织内部未配置Adobe Analytics的人员共享项目链接。 [了解详情](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>要加入私人测试版，请联系您的Adobe客户团队。</p> | 2023年3月15日(Private Beta) | 2023 年 4 月 |

## Adobe Analytics 中的修复

AN-308177； AN-308727； AN-308846； AN-309591； AN-310614； AN-311544； AN-311570； AN-311665； AN-311948； AN-312108； AN-312114； AN-312142； AN-312143； AN-312389； AN-312391； AN-312431； AN-312453； AN-312454； AN-312458； AN-312503； AN-312533； AN-312682； AN-312698； AN-312714； AN-312738； AN-312807 AN-312829； AN-312849； AN-312875； AN-312980； AN-312997； AN-313059； AN-313077； AN-313110； AN-313195； AN-313196； AN-313258； AN-313554； AN-313580； AN-313702； AN-313820； AN-313844； AN-313859； AN-313879； AN-314273； AN-； AN-； AN-； AN-； AN-； AN-

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **由于 Google 客户端提示而更新设备查找** | 2023 年 2 月 27 日 | 计划于 2023 年 2 月 16 日使用的客户端提示功能被推迟，以更好地确保使用提示查找设备的质量。我们于2023年2月27日开始了发布的第一阶段，以支持客户端提示。 发布的第二阶段（也是最后一阶段）于2023年3月2日星期四完成。 [了解详情](/help/technotes/client-hints.md) |
| **Analytics Source Connector 可用性** | 2023 年 2 月 15 日 | 2023年2月28日，位于加拿大的新Adobe Experience Platform数据中心提供了Analytics Source Connector。 |
| **自动迁移到“分类集”架构** | 2023 年 2 月 8 日 | 在接下来的几个月里，Adobe 计划将所有组织的所有分类迁移到最新的分类架构。最后一批迁移的客户估计会在 2023 年 5 月发生。无需客户操作，预计不会出现停机时间。这种新架构有很多好处，包括：<ul><li>大幅缩短处理时间（72 小时 → 24 小时）</li><li>能够使用[分类集](/help/components/classifications/sets/overview.md) UI</li><li>未来通过[适用于分类数据的 Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=zh-Hans) 在 Adobe Experience Platform 中使用分类数据的选项</li></ul>请注意以下可能会影响您组织工作流的变更：<ul><li>使用浏览器或 FTP 导入时，始终启用“[!UICONTROL 冲突时覆盖]”。</li><li>使用浏览器或 FTP 导入时，不再支持导入后立即导出的选项。</li><li>Analytics 2.0 API `GetDimensions`端点现在返回用于分类的字符串标识符，而不是数字标识符。仍然可以使用数字标识符，但 Adobe 建议尽可能使用新的字符串标识符。可以使用 `?expansion=hidden` 查询字符串参数检索数字标识符。</li></ul>如果您想为您的组织制定更具体的迁移计划，或者对此迁移有疑问/疑虑，请联系 Adobe 客户关怀。[了解详情](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023年12月31日，我们将终止许多相关的Reports &amp; Analytics功能，其中包括但不限于：计划报表、数据提取和DL报表。 2023年12月31日之后，将不再发送任何计划报告。 In **2023年4月**，任何计划于2023年12月31日之后到期的报告将自动更新并恢复到2023年12月31日到期。 此外，您也无法再安排在2023年12月31日之后生成报告。 |
| **生命周期结束 [!UICONTROL 人员] 量度** | 2023 年 2 月 28 日 | 弃用 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html)，与设备协作相关的人员量度不再相关。 在不久的将来（日期待定），我们将删除此 [!UICONTROL 人员] 量度。 到那时，我们将其数据重定向到 [!UICONTROL 独特访客] 量度以防止项目、区段和计算量度中断。<p>**注释**：此 [[!UICONTROL 人员] 与跨设备分析绑定的量度](/help/components/metrics/people.md) 不受此公告的影响。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为Reports &amp; Analytics EOL的一部分， [!UICONTROL 发布列表] 计划终止使用 **2023年12**. 您将无法创建新或访问现有 [!UICONTROL 发布列表] 发送或计划 [!UICONTROL Analysis Workspace] 个项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 客户经理联系。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
