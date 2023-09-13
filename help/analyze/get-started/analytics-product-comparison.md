---
description: Analysis Workspace、Reports & Analytics、Report Builder、Data Warehouse 和 Data Workbench 的系统要求和比较
title: Analytics 产品比较和要求
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 0579715d33db28f1741eed2b1aa1520d3beb757b
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 97%

---

# Analytics 产品比较和要求

此页面包含各种 Adobe Analytics 产品的比较：Analysis Workspace、Reports &amp; Analytics、Report Builder、Data Warehouse、Data Workbench、数据馈送和 Analytics API 2.0。

有关使用哪种 Adobe Analytics 产品的信息，请参阅[我应该使用哪种 Adobe Analytics 工具？](/help/analyze/get-started/which-analytics-tool.md)。

| 产品名称和帮助链接 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html?lang=zh-Hans) | [数据馈送](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **访问方法** | [浏览器](/help/analyze/get-started/sys-reqs.md) | [浏览器](/help/analyze/get-started/sys-reqs.md) | [Windows 版 MS Excel](/help/analyze/report-builder/setup/system-requirements.md) | 通过浏览器进行安装。[了解详情](/help/analyze/get-started/sys-reqs.md) | [Windows 64 位](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=zh-Hans) | 通过浏览器进行安装。[了解详情](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API 工具。使用 Adobe Developer 凭据登录。[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **数据粒度** | 汇总 | 汇总 | 汇总 | 汇总 | 点击 | 点击 | 汇总 |
| **Experience Cloud ID (ECID) 可用** | 否 | 否 | 否 | 是 | 是 | 是 | 否 |
| **时间戳可用** | 否 | 否 | 否 | 否 | 是 | 是 | 否 |
| **处理级别** | 完全处理 | 完全处理，具有单独的[实时报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | 完全处理，具有单独的[实时报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | 完全处理 | 完全处理 | 完全处理 | 完全处理 |
| **包含管理员机器人过滤器数据**<br> [了解详情](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | 否 | 是 - 单独的机器人报告 | 是 - 单独的机器人报告 | 否 | 否 | 否 | 否 |
| **显示低流量（超出唯一值）**<br> [了解详情](/help/technotes/low-traffic.md) | 是 | 是 | 是 | 否 | 否 | 否 | 是 |
| **可见的行限制（分页前）** | 400 | 200 | 50000 | 无限制 | 无限制 | 无限制 | 50000 |
| **多个报告包** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 是，具有限制 | 是 | 否 | 是 | 否 | 是 |
| **划分数** | 无限制 | 最高 2 | 最高 2 | 无限制 | 无限制 | 无限制 | 无限制，跨多个查询运行 |
| **区段划分** <br> [了解详情](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | 是 | 是 | 是 | 是，具有[限制](/help/components/segmentation/seg-reference/seg-compatibility.md) | 是 | 否 | 是 |
| **计算指标** <br> [了解详情](/help/components/c-calcmetrics/cm-overview.md) | 是，具有[归因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 是 | 是 | 否 | 是 | 否 | 是，具有[归因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **营销渠道** <br> [了解详情](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 是 | 是 | 是 | 是 | 是 | 是 - [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **同类群组分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 否 | 否 | 否 | 是 | 否 | 否 |
| **归因** | 是，具有[归因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 有限制 | 有限制 | 否 | 是 | 否 | 是，具有[归因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Virtual Analyst 功能**<br> [了解详情](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | 是 | 否 | 否 | 否 | 否 | 否 | 是 |
| **策划**<br> [了解详情](/help/analyze/analysis-workspace/curate-share/curate.md) | 是 - 项目和 VRS | 否 | 否 | 否 | 否 | 否 | 是 - 仅 VRS |
| **项目共享**<br> [了解详情](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，具有项目角色 | 是 | 是 | 否 | 是 | 否 | 否 |
| **计划提交** | 是 | 是 | 是 | 是 | 否 | 是 | 否 |
| **提交目标** | 电子邮件 | 电子邮件 | 电子邮件、FTP、SFTP、[发布到 Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Amazon S3、Google Cloud Platform、Azure SAS、Azure RBAC和电子邮件 | - | Amazon S3、Azure RBAC、Azure SAS 和 Google Cloud Platform | - |
| **VRS 报告时间处理**<br> [了解详情](/help/components/vrs/vrs-report-time-processing.md) | 是 | 否 | 否 | 否 | 否 | 否 | 是 |
