---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: bdafc3218c29f72e97c3748967bd49bc7d0c0af8
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 97%

---

# 当前 Adobe Analytics 发行说明（2023 年 4 月）

**上次更新时间**：2023 年 4 月 21 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## Adobe Analytics 的新增或更新功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **回填非生产沙箱** | 在非生产沙盒中创建Analytics源连接器数据流时，非生产沙盒的回填将限制为3个月。 生产沙箱的工作时间将保持在13个月。 | 不适用 | 2023 年 4 月 26 日 |
| **Analytics 源连接器流式处理的行/列筛选** | Adobe Experience Platform 中的 Analytics 源连接器现在允许过滤 Analytics 数据，这些数据用于填充[实时客户配置文件](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)中的配置文件。行级过滤有助于减少与配置文件关联的事件数。列级过滤有助于减少事件本身的丰富性，从而使您能够优化对配置文件权利的使用。此过滤仅适用于发送至实时客户配置文件和[标识服务](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hans)的数据。**过滤不会影响发送到数据湖以用于 Customer Journey Analytics** 等应用程序的数据。[了解详情](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans#filtering-for-profile) | 不适用 | 2023 年 3 月 29 日 |
| **Web SDK 对 Activity Map 的部分支持** | 从 Web SDK 版本 2.15.0 开始，我们开始在启用链接跟踪时填充 Activity Map 数据。这样使得 Web SDK 用户如果用在 Analytics 中配置的 Web SDK 和 Activity Map 启用了链接跟踪，则可获得 Activity Map 报告。<p>当客户从一个页面导航到下一个页面时，用 Web SDK 启用链接跟踪当前将发送链接事件。这与 AppMeasurement 的工作方式不同，并且可能会导致将额外的可计费点击数发送到 Adobe。请在[此处](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html)和[此处](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)了解详情 | 不适用 | 2023 年 3 月 31 日 |
| **Experience Edge 的 IP 地址模糊处理** | Experience Edge 将支持对直接发送到 Adobe Experience Platform 的数据进行 IP 地址模糊处理。这有利于将数据直接发送到 Platform 以用于 CJA 或其他 Platform 解决方案的客户。 IP 地址模糊处理是在数据流级别配置的。它支持删除最后一个八位字节或整个 IP 地址。<p>**注释**：模糊处理不适用于发送到 Adobe Analytics 的数据。Analytics 继续获取完整的 IP。IP 处理继续在 Analytics 中单独完成。将来，我们计划允许在 Edge 模糊分析数据。 | 不适用 | AEP 于 2023 年 4 月 26 日发布 |
| **Analysis Workspace 中的数据词典** | 数据词典可帮助用户和管理员跟踪、管理并更好地了解其 Analytics 环境中的组件（如维度、量度等）。[了解详情](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 15 日 | 2023 年 3 月 29 日 |
| **项目链接共享（无需登录）** - 仅限访问 Private Beta | <p>您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。您可以与组织外的人员或组织内未配置 Adobe Analytics 的人员共享项目链接。[了解详情](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>要加入 Private Beta，请联系您的 Adobe 账户团队。</p> | 2023 年 4 月 26 日 | 2023 年 6 月 |
| 面向 Adobe Analytics 2.0 API 的 2 个新端点指南 | <ul><li>[Analytics 维度 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[Analytics 量度 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> | 不适用 | 2023 年 4 月 10 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了数据馈送中 Operating System.tsv 查找文件的问题。
* 修复了 Reports and Analytics 与 Workspace 之间指标值不同的问题 (AN-315965)。
* 修复了无法导入部分分类的问题。(AN-315854)
* 修复了 Analytics API 1.4 的问题。(AN-316475)
* 修复了阻止某些客户通过 Report Builder 和 Report and Analytics 获取页面维度分类的问题。(AN-314445)
* 修复了无法转移警报的问题。(AN-306457)

### 其他修复

AN-288373、AN-305144、AN-309023、AN-310466、AN-311686、AN-311705、AN-312018、AN-312105、AN-312116、AN-312191、AN-312502、AN-312737、AN-312854、AN-312991、AN-313253、AN-313275、AN-313278、AN-313282、AN-313365、AN-313390、AN-313547、AN-313549、AN-313818、AN-313986、AN-314080、AN-314248、AN-314251、AN-314262、AN-314300、AN-314309、AN-314448、AN-314643、AN-314564、AN-314645、AN-314705、AN-314761、AN-314831、AN-314919、AN-314948、AN-315032、AN-315115、AN-315154、AN-315158、AN-315321、AN-315375、AN-315379、AN-315392、AN-315407、AN-315427、AN-315582、AN-315591、AN-315699、AN-315700、AN-315704、AN-315705、AN-315777、AN-315923、AN-316237、AN-316243、AN-316324、AN-316415、AN-316474、AN-316493、AN-316596、AN-316864；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **设备查找过程现在将一个第三方用于所有设备查找** | 2023 年 3 月 3 日 | 2023 年 3 月 2 日，作为推出客户端提示支持的一部分，我们更新了设备查找过程以将一个第三方用于所有设备查找。我们以前将该第三方仅用于移动设备查找。在此推出的过程中，不当地为一些桌面操作系统标注了“mobile”一词（如“Mobile OS X 10.15.7”而非“OS X 10.15.7”）。<p>在 Adobe 的 4 月发行版中，我们将更正这些名称。将追溯地更新 Analytics 和 CJA 报告，因为其报告基于作为事件数据的一部分而记录的 ID 查找操作系统名称。在更新与 ID 对应的查找值后，将更正所有报告，包括历史数据。对于[!UICONTROL 数据馈送]客户，如果您在报告时使用类似的查找过程，则更改可追溯。不过，如果您将操作系统值存储在事件数据中，则报告将仅在以后更新。有关更多详细信息，请参阅[操作系统](/help/components/dimensions/operating-systems.md)。 |
| **由于 Google 客户端提示而更新设备查找** | 2023 年 2 月 27 日 | 计划于 2023 年 2 月 16 日使用的客户端提示功能被推迟，以更好地确保使用提示查找设备的质量。我们于 2023 年 2 月 27 日开始了第一阶段的发布，以支持客户端提示功能。2023 年 3 月 2 日（星期四）完成了第二阶段也是最后一阶段的发布。[了解详情](/help/technotes/client-hints.md) |
| **自动迁移到“分类集”架构** | 2023 年 2 月 8 日 | 在接下来的几个月里，Adobe 计划将所有组织的所有分类迁移到最新的分类架构。最后一批迁移的客户估计会在 2023 年 5 月发生。无需客户操作，预计不会出现停机时间。这种新架构有很多好处，包括：<ul><li>大幅缩短处理时间（72 小时 → 24 小时）</li><li>能够使用[分类集](/help/components/classifications/sets/overview.md) UI</li><li>未来通过[适用于分类数据的 Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html) 在 Adobe Experience Platform 中使用分类数据的选项</li></ul>请注意以下可能会影响您组织工作流的变更：<ul><li>使用浏览器或 FTP 导入时，始终启用“[!UICONTROL 冲突时覆盖]”。</li><li>使用浏览器或 FTP 导入时，不再支持导入后立即导出的选项。</li><li>Analytics 2.0 API `GetDimensions`端点现在返回用于分类的字符串标识符，而不是数字标识符。仍然可以使用数字标识符，但 Adobe 建议尽可能使用新的字符串标识符。可以使用 `?expansion=hidden` 查询字符串参数检索数字标识符。</li></ul>如果您想为您的组织制定更具体的迁移计划，或者对此迁移有疑问/疑虑，请联系 Adobe 客户关怀。[了解详情](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **终止日语版功能手机跟踪服务** | 2023 年 3 月 21 日 | 仅针对我们的日本客户：**2023 年 5 月底**&#x200B;将终止日语版功能手机跟踪服务 (mod_ktrack)。由此给您带来的不便，我们深表歉意，但我们恳请您卸载或禁用安装在您 Apache 服务器上的这些模块。请参阅[本文档](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf)中的第 27 页和第 28 页以供参考。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。在 **2023 年 4 月**，任何计划在 2023 年 12 月 31 日之后到期的报告将会自动更新并恢复到 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 人员]指标** | 2023 年 3 月 9 日 | 启用 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html) 后，与 Device Co-op 相关的人员量度不再相关。我们将在 2023 年 5 月 8 日删除[!UICONTROL 人员]量度。届时，我们会将其数据重定向到[!UICONTROL 独特访客]量度，以防止项目、区段和计算量度出现中断。<p>**注释**：与跨设备分析相关的[[!UICONTROL 人员]量度](/help/components/metrics/people.md)不受本公告影响。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports &amp; Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用[!UICONTROL 发布列表]。您将无法创建新的[!UICONTROL 发布列表]或访问现有的发布列表以发送或安排 [!UICONTROL Analysis Workspace] 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
