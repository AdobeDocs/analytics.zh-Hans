---
description: Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse 和 Data Workbench 的系统要求和比较。
title: Analytics 产品比较和要求
translation-type: tm+mt
source-git-commit: 9265fb410b20a764ecc86c56b453b045122fcd05
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 83%

---


# Analytics 产品比较和要求

系统要求，并比较分析工作区、报告和分析、临时分析、报表生成器、数据仓库和数据工作台。

有关使用哪种 Adobe Analytics 产品的信息，请转至[此处](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)。

| 产品名称和帮助链接 | [Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) | [Reports and Analytics](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/reports-analytics/getting-started.html) | [Ad Hoc Analysis](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/ad-hoc-analysis/adhoc-home.html) | [Report Builder](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/zh-Hans/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html) |
|---|---|---|---|---|---|---|
| **访问方法** | 用于构建强大的自定义分析项目和实现分析民主化的浏览器解决方案。 | 用于数字分析的浏览器解决方案。 | 用于高级数字分析的基于 Java 的工具。 | 允许您通过 Reports &amp; Analytics 数据构建自定义请求并使用 Microsoft Excel 实现可视化的 Excel 外接程序。 | 用于生成 .csv 格式报表的浏览器解决方案。可生成表格格式的文件。 | 用于高级分析（如自定义属性建模、预测分析和全方位客户分析）的多渠道分析工具。 |
| **报表划分** | 无限制 | 最多 2 项关联 | 无限制 | 最多 2 项关联 | 执行完全扩展的无限制划分，按区段划分。 | 无限制 |
| **区段比较** | 无限制 | 最多 2 个区段 | 无限制 | 无限制（数据请求堆叠） | 1 个区段。支持多个（堆叠）区段。 | 无限制 |
| **行输出限制** | 400 | 200 | 50,000 | 50,000 | 无限制 | 可自定义 |
| ****&#x200B;唯一值限制（在 eVar/prop 报表内） | 500K-2MM | 500K-2MM | 500K-2MM | 500K-2MM | 无限制 | 可自定义 |
| **漏斗/路径** | 是： [流失](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/流[量](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/reports-analytics/reports.html) | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/ad-hoc-analysis/c-reports-paths.html) | 是 | 否 | 是 |
| **高级客户历程分析** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-landing.html) | 否 | 是 | 否 | 否 | 是 |
| **同类群组分析** | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | 否 | 否 | 否 | 否 | 是 |
| **高级属性** | [归因 IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | 有限制 - 最初/最后/线性 | 有限制 - 最初/最后/线性 | 有限制 - 最初/最后/线性 | 有限制 - 最初/最后/线性 | 是 |
| **增强的可视化选项** | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | 否 | 是 | 是 | 否 | 是 |
| **可自定义的布局** | [是](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) | 是 - [功能板](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | 否 | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | 按划分或按量度对结果排序。 | 是 |
| ****&#x200B;项目管理操作（针对非分析人员简化报表） | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/curate.html) | 否 | 否 | 是 | 否 | 是 |
| **项目共享** | [是： 所有用户](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/curate.html) | [是： 所有用户](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/reports-analytics/scheduling.html) | 仅限“Ad Hoc Analysis”用户 | 是： 所有用户 | 否 | 是 |
| **计划报告** 投放 | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/reports-analytics/scheduling.html) | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/ad-hoc-analysis/c-schedule.html) | [是](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/report-builder/t-schedule-a-data-request.html) | 是 | 是 |
| **系统要求** | 浏<br>[览器更多……](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/sys-reqs.html) | 浏<br>[览器更多……](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/sys-reqs.html) | Java<br>[更多……](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/ad-hoc-analysis/c-getting-started.html) | Windows、MS<br>[ExcelMore...](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | 用于打开 .csv 文件的浏览器或程序，例如 MS Excel。可生成表格格式的文件。 | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/zh-Hans/data-workbench/using/install/c-data-workbench-client-install.html) |
| **虚拟报告套件（报告时间处理）兼容性** | 是 | 是 | 是 | 是 | 否 | 是? |
| **多报表包** | 是 | 否 | 否 | 否 | 否 | 是? |
| **计算量度** | 是 | 是 | 是 | 是 | 是 | 是 |
| **营销渠道兼容性** | 是 | 是 | 是 | 是 | ? | ? |
| **粒度级别** |  |  |  |  |  |  |
| **异常检测** | 是 | 否 |  |  |  |  |
| **贡献分析** | 是 | 否 | 否 | 否 | 否 | 是 |
| **区段类型** |  |  |  |  |  |  |