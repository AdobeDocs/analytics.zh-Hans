---
title: Report Builder 概述
description: 描述 Report Builder 功能
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 100%

---

# Report Builder 概述

新的 Javascript Report Builder 插件最初仅在 Customer Journey Analytics 中提供，现在也被引入到 Adobe Analytics 中。这个新版本有几个优点：

- 通过改进的数据块创建和管理工作流程以及更大的数据块灵活性，更快、更轻松地在 Excel 中获得见解
- 跨平台：使用 Report Builder 无需再登录虚拟机，因为我们现在支持 PC、Mac 和 Excel Online
- API 2.0 升级减少了等待数据块返回的时间
- 速度提高

旧版 Report Builder 工具的用户可以将[旧版工作簿转换](/help/analyze/report-builder/convert-workbooks.md)为新版 Report Builder。

通过 Report Builder，您可以使用 Adobe Analytics 数据轻松创建、编辑和刷新自定义报告。通过 Report Builder 简单灵活的拖放用户界面，您可以在 Excel 中从 Adobe Analytics 数据创建复杂的数据查询和自定义报告。

使用 Report Builder，您可以：

- 引用现有工作表单元格以获得绝佳的行顺序、日期范围或过滤器
- 使用日历、单元格引用或日期数学创建自定义日期
- 使用熟悉的 Excel 格式设置工具设计表格和可视化项

## 并排使用旧版 Report Builder 和新版 Report Builder

您仍然可以使用两个版本的 Report Builder，但需要注意以下事项：

- 切勿同时对同一个文件使用两个版本的 Report Builder。它们是互斥的。
- 您仍然可以在旧版工作簿上使用旧版 Report Builder，在新版工作簿上使用新版 Report Builder。
- 此外，您还可以自动将[旧版工作簿转换](/help/analyze/report-builder/convert-workbooks.md)为新版 Report Builder 格式。在此之前，请复制并重命名该文件。

## 新版 Report Builder 不支持旧版 Report Builder 的功能

如果将旧版 Report Builder 的功能与新版 Report Builder 插件进行比较，某些旧版功能不再可用：

- 实时请求

- 路径/流失报告

- 用于计划报告的 FTP 选项

- 访客量度。以下量度都将转换为“唯一访客”，即使报告结果可能不完全匹配：`visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly` 和 `visitorsyearly`。这也适用于`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` 和 `mobilevisitorsyearly`。

## 常见用例

- **数据提取**：Adobe Report Builder 允许您将 Adobe Analytics 中的数据提取到 Excel 中。您可以创建自定义报告和查询来检索与您的分析相关的特定数据点。

- **自定义报告**：您可以在 Excel 中设计和格式化自定义报告，以满足您的特定报告需求。这对于为不同利益相关者定制报告特别有用。

- **临时分析**：用户可以快速生成临时报告来回答特定问题或探索数据趋势，而无需经历冗长的报告创建过程。

- **仪表板**：从 CJA 提取的数据可用于创建基于 Excel 的仪表板和可视化内容，以提供对关键绩效量度 (KPI) 的高级概述。

- **分享见解**：您可以与可能无法直接访问 CJA 的团队成员或利益相关者共享 Excel 报告和见解。

## 概述视频

>[!IMPORTANT]
>
>此概述视频介绍了 Customer Journey Analytics 中的 Report Builder 用户界面。一些用户界面和术语有所不同。除此以外，用户体验完全相同。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Report Builder 概述](https://video.tv.adobe.com/v/3452590?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

您可以从 [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview) 下载 Report Builder。
