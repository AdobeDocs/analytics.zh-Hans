---
title: 新的Adobe Report Builder是什么？
description: 描述新的Report Builder功能
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 29%

---

# 关于新的Adobe Report Builder

最初仅在Customer Journey Analytics中提供的新JavascriptReport Builder加载项现在也在Adobe Analytics中引入。 此新版本具有以下几个好处：

- 通过改进的数据块创建和管理工作流（包括更大的数据块灵活性），更快、更轻松地在Excel中查找见解
- 跨平台：不再登录虚拟机以使用Report Builder，我们现在支持PC、Mac和Excel Online
- 由于API 2.0升级，等待数据块返回的时间得以缩短
- 速度提高

旧版Report Builder工具的用户可以[将旧版工作簿](/help/analyze/report-builder/convert-workbooks.md)转换为新Report Builder。

通过Report Builder，您可以使用Adobe Analytics数据轻松创建、编辑和刷新自定义报表。 借助Report Builder简单灵活的拖放UI，您可以在Excel中从Adobe Analytics数据创建复杂的数据查询和自定义报表。

通过Report Builder，您可以：

- 引用现有工作表单元格以获得绝佳的行顺序、日期范围或过滤器
- 使用日历、单元格引用或日期数学创建自定义日期
- 使用熟悉的 Excel 格式设置工具设计表格和可视化项

## 并排使用旧版Report Builder和新Report Builder

您仍然可以使用两个版本的Report Builder，但需注意以下事项：

- 不要在同一文件上同时使用两个Report Builder版本。 它们是互斥的。
- 您仍然可以在旧工作簿中使用旧版Report Builder，在新工作簿中使用新Report Builder。
- 此外，您可以自动[将旧工作簿](/help/analyze/report-builder/convert-workbooks.md)转换为新的Report Builder格式。 在执行此操作之前，请复制并重命名文件。

## 新Report Builder中不支持旧版Report Builder功能

将旧版Report Builder的功能与新Report Builder加载项进行比较时，某些旧版功能不再可用：

- 实时请求

- 路径/流失报表

- 计划报表的FTP选项

- 访客量度。 以下量度将全部转换为“独特访客”，即使报表结果可能不完全匹配： `visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly`和`visitorsyearly`。 这也适用于`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly`和`mobilevisitorsyearly`。

## 常见使用案例

- **数据提取**： Adobe Report Builder允许您将数据从Adobe Analytics提取到Excel中。 您可以创建自定义报告和查询来检索与您的分析相关的特定数据点。

- **自定义报告**：您可以在 Excel 中设计和格式化自定义报告，以满足您的特定报告需求。这对于为不同利益相关者定制报告特别有用。

- **临时分析**：用户可以快速生成临时报告来回答特定问题或探索数据趋势，而无需经历冗长的报告创建过程。

- **仪表板**：从 CJA 提取的数据可用于创建基于 Excel 的仪表板和可视化内容，以提供对关键绩效指标 (KPI) 的高级概述。

- **分享见解**：您可以与可能无法直接访问 CJA 的团队成员或利益相关者共享 Excel 报告和见解。

## 概述视频

>[!IMPORTANT]
>
>此概述视频演示了Customer Journey Analytics中的Report Builder用户界面。 某些用户界面和术语有所不同。 否则，用户体验将相同。


>[!BEGINSHADEBOX]

观看![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[Report Builder概述](https://video.tv.adobe.com/v/337569?quality=12&learn=on){target="_blank"}观看演示视频。

>[!ENDSHADEBOX]

您可以从[Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview)下载Report Builder。
