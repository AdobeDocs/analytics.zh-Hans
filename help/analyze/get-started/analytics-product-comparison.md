---
description: Analysis Workspace、Report Builder、Data Warehouse 和 Data Workbench 的系统要求和比较
title: Analytics 产品比较和要求
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# Analytics 产品比较和要求

此页面包含各种 Adobe Analytics 产品的比较：Analysis Workspace、Report Builder、Data Warehouse、数据馈送和 Analytics API 2.0。

有关使用哪种 Adobe Analytics 产品的信息，请参阅[我应该使用哪种 Adobe Analytics 工具？](/help/analyze/get-started/which-analytics-tool.md)。

| 产品名称和帮助链接 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [数据馈送](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **访问方法** | [浏览器](/help/analyze/get-started/sys-reqs.md) | [Windows 版 MS Excel](/help/analyze/legacy-report-builder/setup/system-requirements.md) | 通过浏览器进行安装。[了解详情](/help/analyze/get-started/sys-reqs.md) | 通过浏览器进行安装。[了解详情](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API 工具。使用 Adobe Developer 凭据登录。[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **数据粒度** | 汇总 | 汇总 | 汇总 | 点击 | 汇总 |
| **Experience Cloud ID (ECID) 可用** | 否 | 否 | 是 | 是 | 否 |
| **时间戳可用** | 否 | 否 | 否 | 是 | 否 |
| **处理级别** | 完全处理 | 完全处理，具有单独的[实时报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | 完全处理 | 完全处理 | 完全处理 |
| **包含管理员机器人过滤器数据**<br> [了解详情](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | 否 | 是 - 单独的机器人报告 | 否 | 否 | 否 |
| **显示低流量（超出唯一值）**<br> [了解详情](/help/technotes/low-traffic.md) | 是 | 是 | 否 | 否 | 是 |
| **可见的行限制（分页前）** | 400 | 50000 | 无限制 | 无限制 | 50000 |
| **多个报告包** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 是 | 否 | 是 | 否 | 是 |
| **划分数** | 无限制 | 最高 2 | 无限制 | 无限制 | 无限制，跨多个查询运行 |
| **区段划分** <br> [了解详情](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | 是 | 是 | 是，具有[限制](/help/components/segmentation/seg-reference/seg-compatibility.md) | 否 | 是 |
| **计算指标** <br> [了解详情](/help/components/c-calcmetrics/cm-overview.md) | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) | 是，具有归因 | 是 | 否 | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) |
| **营销渠道** <br> [了解详情](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 是 | 是 | 是 | 是 - [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **同类群组分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 是 | 否 | 否 | 否 |
| **归因** | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) | 有限制 | 否 | 否 | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) | 否 |
| **策划**<br> [了解详情](/help/analyze/analysis-workspace/curate-share/curate.md) | 是 - 项目和虚拟报告包 | 否 | 否 | 否 | 是 - 仅限虚拟报告包 |
| **项目共享**<br> [了解详情](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，具有项目角色 | 是 | 否 | 否 | 否 |
| **计划提交** | 是 | 是 | 是 | 是 | 否 |
| **提交目标** | 电子邮件 | 电子邮件、FTP、SFTP、[发布到 Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3、Google Cloud Platform、Azure SAS、Azure RBAC 和电子邮件 | Amazon S3、Azure RBAC、Azure SAS 和 Google Cloud Platform | - |
| **虚拟报告包报告时间处理**<br> [了解详情](/help/components/vrs/vrs-report-time-processing.md) | 是 | 否 | 否 | 否 | 是 |
