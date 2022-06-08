---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9a16f3942505028624e5c07568342a9acac898d7
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 63%

---

# 当前 Adobe Analytics 发行说明（2022 年 5 月）

**上次更新**:2022年6月8日

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 中的新增功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| 通过 Experience Edge 填充生命周期维度和量度 | Analytics 报表中现在将显示通过 Experience Edge 发送的移动生命周期数据。查看文档，详细了解通过 Experience Edge 收集哪些生命周期数据以及这些数据如何与现有生命周期报表相对应。[了解详情 - 即将推出] | 2022 年 5 月 27 日 |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics 中的修复

（适用于多个客户的修复）

不适用

### Adobe Analytics 中的其他修复

（适用于单个客户的修复）

AN-274429、AN-279640、AN-280918、AN-280945、AN-282884、AN-283565、AN-284785、AN-284814、AN-284854、AN-284989、AN-285244、AN-285253、AN-285432、AN-285528、AN-285535、AN-285710、AN-286255、AN-286340、AN-286434、AN-286454、AN-286630、AN-286716、AN-286854、AN-286911

### Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 在Reports &amp; Analytics中暂停计划报表 | 2022年6月8日 | 2022年4月21日，我们宣布弃用计划报表的几项功能，以便为之前宣布的 [Reports &amp; Analytics生命周期终止](https://express.adobe.com/page/6WnF8JK6IRDhf/). 这些功能包括计划新报表和新数据提取的功能。<p>为响应寻求扩展并简化从Reports and Analytics迁移的客户请求，我们决定将这些功能的访问权限扩展到 **2023年1月31日**. 请注意，报告和数据提取的过期时间窗口将继续限制为9个月；除非重新激活计划，否则在此时段结束时，报表和数据提取提交将会暂停。 <p>重申一遍，这些功能将于2023年1月31日被弃用，在此之前，您需要将计划报表迁移到Adobe Analytics中可用的其他机制之一。 如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。 |
| 在Report Builder中暂停计划任务 | 2022年6月8日 | 2022年4月21日，我们对Report Builder中的计划任务进行了更改，以此作为性能和交付优化工作的一部分。 这些更改包括删除使计划投放“在x次发生后结束”的功能。 为响应一些客户请求寻求更多时间来探索和实施替代方案，我们决定以有限的方式恢复此选项，直到 **2023年1月31日**.<p>您将能够继续安排每小时Report Builder任务，并在最多99次发生后结束这些任务。 请注意，回滚仅适用于每小时任务；“x次出现后结束”将不可用于所有其他提交间隔（每日、每周、每月和每年）。 请注意，此选项将于2023年1月31日被弃用。 如需更多问题或支持，请联系Adobe客户关怀团队。 |
| **SFTP 升级** | 2022 年 5 月 9 日 | 之前，我们已告知 Adobe 将在 2022 年 5 月升级其安全文件传输协议 (SFTP) 服务以提高文件传输的安全性。我们已将此升级推迟到 **2022年夏季**. 完成此更改后，将不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **更新某些客户支持的浏览器加密方法** | 2022 年 3 月 28 日 | Adobe 提供两种密码安全级别，以满足客户对第一方数据收集安全性的不同需求。在 **2022 年 6 月 23 日**，对于将其安全级别设置为“高”的客户不再支持某些 HTTPS 加密算法（也称为密码）。此操作意味着某些旧版操作系统无法再将数据发送到 Analytics，因为它们不支持新型加密方法。不影响使用默认“标准”密码安全设置的客户。已直接联系所有当前正在使用“高”设置的客户。可在此处找到受此更改影响的密码的详细列表。 |
| **2022 年 ISO 区域更新** | 2021 年 3 月 11 日 | Adobe 打算在 **2022 年 6 月 10 日**&#x200B;执行 2022 年 ISO 区域更新。预计在此次发布后将看到少量地理信息更新。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

