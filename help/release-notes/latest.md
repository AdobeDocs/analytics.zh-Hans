---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5739b9bd20d63c51343127832778c4c3836993b3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 当前 Adobe Analytics 发行说明 (2023 年 3 月)

**上次更新日期**：2023 年 3 月 10 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## Adobe Analytics 的新增或更新功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace 中的数据词典** | 数据词典可帮助用户和管理员跟踪、管理并更好地了解其 Analytics 环境中的组件（如维度、量度等）。[了解详情](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 15 日 | 2023 年 3 月 22 日 |
| **移动仪表板中的数据故事** | 数据故事让您可以将多个可自定义的详细信息视图添加到移动记分卡项目中的图块。使用数据故事深入了解关键驱动因素、相关指标以及客户历程中的不同步骤。您可以轻松浏览这些视图以了解关键指标背后的整个故事。[了解详情](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | 不适用 | 2023 年 3 月 8 日 |
| **计划项目的过期日期** | 无论计划频率如何，您都可以将计划项目的最长到期日期设置为最多一年。 | 不适用 | 2023 年 3 月 8 日 |
| **项目链接共享（无需登录）** - 仅限访问 Private Beta | <p>您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。您可以与组织外的人员或组织内未配置 Adobe Analytics 的人员共享项目链接。[了解详情](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>要加入 Private Beta，请联系您的 Adobe 账户团队。</p> | 2023 年 3 月 15 日 (Private Beta) | 2023 年 4 月 |
| **面板日期范围更新** | 在 Workspace 中，我们对以下方面作出了改进：<ul><li>从2月版开始，维度项目和数据预览基于面板日期范围，而不是最近90天。 </li><li>列出的所有维度项都基于面板日期范围内的数据。 如果维度项的数据超出日期范围，则可以在列表底部显示超出日期范围的其他数据。</li><li>没有数据的Dimension可以显示在左边栏中。 单击显示更多选项以查看数据在面板日期范围之外的维度项。</li><li>区段和计算量度生成器中的数据预览基于面板日期范围，除非从组件管理器访问，组件管理器没有关联的面板，并且仍基于过去90天。</li><li>数据预览根据面板日期范围显示数据或组件。</li></ul> | 不适用 | 2023 年 2 月 8 日 |

## Adobe Analytics 中的修复

-308177；AN-308727；AN-308846；AN-309591；AN-310614；AN-311544；AN-311570；AN-311665；AN-311948；AN-312108；AN-312114；AN-312142；AN-312143；AN-312389；AN-312391；AN-312431；AN-312453；AN-312454；AN-312458；AN-312503；AN-312533；AN-312682；AN-312698；AN-312714；AN-312738；AN-312807；AN-312829；AN-312849；AN-312875；AN-312980；AN-312997；AN-313059；AN-313077；AN-313110；AN-313195；AN-313196；AN-313258；AN-313554；AN-313580、AN-；AN-313702；AN-313820；AN-313844；AN-313859；AN-313879；AN-314273

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **由于 Google 客户端提示而更新设备查找** | 2023 年 2 月 27 日 | 计划于 2023 年 2 月 16 日使用的客户端提示功能被推迟，以更好地确保使用提示查找设备的质量。我们于 2023 年 2 月 27 日开始了第一阶段的发布，以支持客户端提示功能。2023 年 3 月 2 日（星期四）完成了第二阶段也是最后一阶段的发布。[了解详情](/help/technotes/client-hints.md) |
| **Analytics Source Connector 可用性** | 2023 年 2 月 15 日 | 2023 年 2 月 28 日，位于加拿大的新 Adobe Experience Platform 数据中心提供了 Analytics Source Connector。 |
| **自动迁移到“分类集”架构** | 2023 年 2 月 8 日 | 在接下来的几个月里，Adobe 计划将所有组织的所有分类迁移到最新的分类架构。最后一批迁移的客户估计会在 2023 年 5 月发生。无需客户操作，预计不会出现停机时间。这种新架构有很多好处，包括：<ul><li>大幅缩短处理时间（72 小时 → 24 小时）</li><li>能够使用[分类集](/help/components/classifications/sets/overview.md) UI</li><li>未来通过[适用于分类数据的 Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html) 在 Adobe Experience Platform 中使用分类数据的选项</li></ul>请注意以下可能会影响您组织工作流的变更：<ul><li>使用浏览器或 FTP 导入时，始终启用“[!UICONTROL 冲突时覆盖]”。</li><li>使用浏览器或 FTP 导入时，不再支持导入后立即导出的选项。</li><li>Analytics 2.0 API `GetDimensions`端点现在返回用于分类的字符串标识符，而不是数字标识符。仍然可以使用数字标识符，但 Adobe 建议尽可能使用新的字符串标识符。可以使用 `?expansion=hidden` 查询字符串参数检索数字标识符。</li></ul>如果您想为您的组织制定更具体的迁移计划，或者对此迁移有疑问/疑虑，请联系 Adobe 客户关怀。[了解详情](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。在 **2023 年 4 月**，任何计划在 2023 年 12 月 31 日之后到期的报告将会自动更新并恢复到 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 人员]指标** | 2023 年 3 月 9 日 | 随着对 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html) 的弃用，与 Device Co-op 相关的人员量度将会不再相关。2023年5月8日，我们将删除 [!UICONTROL 人员] 量度。 届时，我们会将其数据重定向到[!UICONTROL 独特访客]量度，以防止项目、区段和计算量度出现中断。<p>**注释**：与跨设备分析相关的[[!UICONTROL 人员]量度](/help/components/metrics/people.md)不受本公告影响。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports &amp; Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用[!UICONTROL 发布列表]。您将无法创建新的[!UICONTROL 发布列表]或访问现有的发布列表以发送或安排 [!UICONTROL Analysis Workspace] 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
