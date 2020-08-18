---
description: Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse 和 Data Workbench 的系统要求和比较。
title: Analytics 产品比较和要求
translation-type: tm+mt
source-git-commit: 8a48a5bd9e7ef38ffc90ecb9c640166bb3ac4405
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 54%

---


# Analytics产品比较和要求

本页包含各种Adobe Analytics产品的比较：Analysis Workspace、Reports &amp; Analytics、Report Builder、Data warehouse、Data Workbench、数据源和Analytics API 2.0。

有关使用哪种 Adobe Analytics 产品的信息，请转至[此处](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)。

| 产品名称和帮助链接 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports and Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/zh-Hans/data-workbench/using/home.html) | [数据馈送](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **访问方法** | [浏览器](/help/admin/sys-reqs.md) | [浏览器](/help/admin/sys-reqs.md) | [Windows版MS Excel](/help/analyze/report-builder/setup/system-requirements.md) | 通过浏览器进行设置。 [了解更多](/help/admin/sys-reqs.md) | [Windows 64位](https://docs.adobe.com/content/help/zh-Hans/data-workbench/using/install/c-data-workbench-client-install.html) | 通过浏览器进行设置。 [了解更多](/help/export/analytics-data-feed/data-feed-overview.md) | REST风格的API工具。 使用AdobeI/O凭据登录。 [了解更多](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **数据粒度** | 汇总 | 汇总 | 汇总 | 汇总 | 点击 | 点击 | 汇总 |
| **Experience CloudID(ECID)可用** | 否 | 否 | 否 | 是 | 是 | 是 | 否 |
| **可用时间戳** | 否 | 否 | 否 | 否 | 是 | 是 | 否 |
| **处理级别** | 完全处理 | 完全处理，单独 [的实时报告](/help/components/c-real-time-reporting/realtime.md) | 完全处理，单独 [的实时报告](/help/components/c-real-time-reporting/realtime.md) | 完全处理 | 完全处理 | 完全处理 | 完全处理 |
| **包含管理员机器人过滤器数据** <br> [了解更多](/help/admin/admin/bot-removal/bot-removal.md) | 否 | 是——单独的机器人报告 | 是——单独的机器人报告 | 否 | 否 | 否 | 否 |
| **流量低（超出唯一值）** <br> [了解更多](/help/technotes/low-traffic.md) | 是 | 是 | 是 | 否 | 否 | 否 | 是 |
| **可见行限制（分页前）** | 400 | 200 | 50000 | 无限制 | 无限制 | 无限制 | 50000 |
| **多个报表包** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 是，但有限制 | 是 | 否 | 是 | 否 | 是 |
| **划分数** | 无限制 | 最高 2 | 最高 2 | 无限制 | 无限制 | 无限制 | 无限制，跨多个查询 |
| **区段划分** <br> [了解更多](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | 是 | 是 | 是 | 是，但有限 [制](/help/components/segmentation/seg-reference/seg-compatibility.md) | 是 | 否 | 是 |
| **计算量度** <br> [了解更多](/help/components/c-calcmetrics/cm-overview.md) | 是，带 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 是 | 是 | 否 | 是 | 否 | 是，带 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **营销渠道** <br> [了解更多](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 是 | 是 | 是 | 是 | 是 | 是- [va_finder、va_cler](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **群组分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 否 | 否 | 否 | 是 | 否 | 否 |
| **归因** | 是，带 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 有限 | 有限 | 否 | 是 | 否 | 是，带 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **虚拟分析师功能** <br> [了解更多](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | 是 | 否 | 否 | 否 | 否 | 否 | 是 |
| **特选** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/curate.md) | 是——项目和VRS | 否 | 否 | 否 | 否 | 否 | 是 -仅限VRS |
| **项目共享** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，具有项目角色 | 是 | 是 | 否 | 是 | 否 | 否 |
| **计划交付** | 是 | 是 | 是 | 是 | 否 | 是 | 否 |
| **投放目标** | 电子邮件 | 电子邮件 | 电子邮件、FTP、SFTP、 [发布到Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | 电子邮件、FTP。 联系客户关怀以获得其他目标支持，包括SFTP、Azure Blob、AmazonS3 | - | FTP、SFTP、Azure Blob、AmazonS3 | - |
| **VRS报告时间处理** <br> [了解更多](/help/components/vrs/vrs-report-time-processing.md) | 是 | 否 | 否 | 否 | 否 | 否 | 是 |
