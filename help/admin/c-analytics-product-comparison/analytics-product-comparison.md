---
description: Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse 和 Data Workbench 的系统要求和比较。
title: Analytics 产品比较和要求
translation-type: tm+mt
source-git-commit: 54d6b4c2993c5b0391b9243c76661db1da4087b8
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 54%

---


# Analytics 产品比较和要求

本页包含各种Adobe Analytics产品的比较： Analysis Workspace、报告和Analytics、Report Builder、Data warehouse、Data Workbench、数据源和AnalyticsAPI 2.0。

有关使用哪种 Adobe Analytics 产品的信息，请转至[此处](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)。

| 产品名称和帮助链接 | [Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) | [Reports and Analytics](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/zh-Hans/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html) | [数据馈送](https://docs.adobe.com/content/help/zh-Hans/analytics/export/analytics-data-feed/data-feed-overview.html) | [AnalyticsAPI 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **访问方法** | [浏览器](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/sys-reqs.html) | [浏览器](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/sys-reqs.html) | [Windows版MS Excel](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | 通过浏览器进行设置。 [了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/sys-reqs.html) | [Windows 64位](https://docs.adobe.com/content/help/zh-Hans/data-workbench/using/install/c-data-workbench-client-install.html) | 通过浏览器进行设置。 [了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/export/analytics-data-feed/data-feed-overview.html) | REST风格的API工具。 使用AdobeI/O凭据登录。 [了解更多](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **数据粒度** | 汇总 | 汇总 | 汇总 | 汇总 | 点击 | 点击 | 汇总 |
| **可用的过期云ID(ECID)** | 否 | 否 | 否 | 是 | 是 | 是 | 否 |
| **可用时间戳** | 否 | 否 | 否 | 否 | 是 | 是 | 否 |
| **处理级别** | 完全处理 | 完全处理，单独 [的实时报告](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | 完全处理，单独 [的实时报告](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | 完全处理 | 完全处理 | 完全处理 | 完全处理 |
| **包含管理员机器过滤器数据**<br>[了解更多](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | 否 | 是——单独的机器人报告 | 是——单独的机器人报告 | 否 | 否 | 否 | 否 |
| **出现流量不足（超出唯一值）** 了 <br>[解详情](https://docs.adobe.com/content/help/zh-Hans/analytics/technotes/low-traffic.html) | 是 | 是 | 是 | 否 | 否 | 否 | 是 |
| **可见行限制（分页前）** | 400 | 200 | 50000 | 无限制 | 无限制 | 无限制 | 50000 |
| **多个报表包** | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | 是，但有限制 | 是 | 否 | 是 | 否 | 是 |
| **划分数** | 无限制 | 最高 2 | 最高 2 | 无限制 | 无限制 | 无限制 | 无限制，跨多个查询 |
| **细分** 了 <br>[解更多](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | 是 | 是 | 是 | 是，但有限 [制](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | 是 | 否 | 是 |
| **计算指标**<br>[了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/cm-overview.html) | 是，带 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | 是 | 是 | 否 | 是 | 否 | 是，带 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **营销渠道**<br>[了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/components/marketing-channels/c-getting-started-mchannel.html) | 是 | 是 | 是 | 是 | 是 | 是- [va_finder、va_cler](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html) | 是 |
| **群组分析** | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | 否 | 否 | 否 | 是 | 否 | 否 |
| **归因** | 是，带 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | 有限 | 有限 | 否 | 是 | 否 | 是，带 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **虚拟分析师功能**<br>[了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/virtual-analyst/overview.html) | 是 | 否 | 否 | 否 | 否 | 否 | 是 |
| **特选** 了 <br>[解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/curate.html) | 是——项目和VRS | 否 | 否 | 否 | 否 | 否 | 是 -仅限VRS |
| **项目共享**<br>[了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | 是，具有项目角色 | 是 | 是 | 否 | 是 | 否 | 否 |
| **计划交付** | 是 | 是 | 是 | 是 | 否 | 是 | 否 |
| **投放目标** | 电子邮件 | 电子邮件 | 电子邮件、FTP、SFTP、 [发布到Microsoft PowerBI](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/publish-powerbi/power-bi.html) | 电子邮件、FTP。 联系客户关怀以获得其他目标支持，包括SFTP、Azure Blob、AmazonS3 | - | FTP、SFTP、Azure Blob、AmazonS3 | - |
| **VRS报告时间处理了**<br>[解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | 是 | 否 | 否 | 否 | 否 | 否 | 是 |
