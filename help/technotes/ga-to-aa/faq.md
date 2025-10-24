---
title: 迁移到 Adobe Analytics 的常见问题解答
description: 获取有关从第三方平台迁移到 Adobe 的常见问题解答。
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 58d53d6013abcd7d99f2c3cb640d6a648a4ef360
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 53%

---

# 迁移到 Adobe Analytics 的常见问题解答

**如何将历史数据从第三方平台迁移到 Adobe Analytics？**

每个 Analytics 平台都有不同的数据收集、处理和存储方式。Adobe 建议建立明确的截止日期，以便开始在 Adobe Analytics 中收集和使用数据，而不是迁移历史数据。经常使用的截止日期是财政年度的开始、日历年的开始或日历月的开始。如果用户希望查看历史数据，则可登录第三方平台以获取任何特定的历史报告需求。

如果贵组织坚决要求将历史数据迁移到Adobe，请联系您的Adobe客户团队。 实施顾问可以与您的组织合作，将 Google Analytics 数据导出转换为可由 Adobe 数据收集服务器引入的数据源。

对于移动历史数据，建议使用[Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-overview)，它可以引入任何全渠道数据源。

**我习惯使用许多报表中的分段下拉列表。 如何在 [!UICONTROL Analysis Workspace] 中重新创建分段下拉菜单？**

下拉筛选器是[!UICONTROL Analysis Workspace]中一项灵活而强大的功能，允许使用分段下拉列表。 在工作区项目中时：

1. 对要包含在下拉筛选器中的组件使用&#x200B;***ctrl***+***click*** (Windows)或&#x200B;***cmd***+***click*** (Mac)。 不仅仅限于区段。 任何组件都可以包含在下拉过滤器中。
2. 将组件组拖到标有&#x200B;*在此处放置区段*&#x200B;的工作区区域中。 放手前，按住&#x200B;**[!UICONTROL Shift]**。

访问此[!UICONTROL Workspace]项目的用户现在可以使用此下拉筛选器将区段或其他组件应用到该项目。 有关更多信息，请参阅 Adobe Analytics 工具指南中的[面板概述](/help/analyze/analysis-workspace/c-panels/panels.md)。

**我习惯通过单击维度项目来查看深入信息。如何在 Analysis Workspace 中重现这种轻松的工作流？**

[!UICONTROL Analysis Workspace] 中的维度项目还具有一个轻松的划分工作流。使用维度项的上下文菜单访问划分。 然后选择&#x200B;**[!UICONTROL 划分]**&#x200B;和所需的组件。 您可以对每个值使用&#x200B;***ctrl***+***select*** (Windows)或&#x200B;***cmd***+***select*** (Mac)，将相同的划分应用于多个维度项目。
