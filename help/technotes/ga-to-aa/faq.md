---
title: 迁移到 Adobe Analytics 的常见问题解答
description: 获取有关从第三方平台迁移到 Adobe 的常见问题解答。
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 95%

---

# 迁移到 Adobe Analytics 的常见问题解答

**如何将历史数据从第三方平台迁移到 Adobe Analytics？**

每个 Analytics 平台都有不同的数据收集、处理和存储方式。Adobe 建议建立明确的截止日期，以便开始在 Adobe Analytics 中收集和使用数据，而不是迁移历史数据。经常使用的截止日期是财政年度的开始、日历年的开始或日历月的开始。如果用户希望查看历史数据，则可登录第三方平台以获取任何特定的历史报告需求。

如果您的组织坚决要求将历史数据移植到Adobe，请联系您的Adobe客户团队。 实施顾问可以与您的组织合作，将 Google Analytics 数据导出转换为可由 Adobe 数据收集服务器引入的数据源。

若要移动历史数据，我们建议使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans)，它可以引入任何全渠道数据源。

**我习惯使用许多报表中都有的分段下拉菜单。如何在 [!UICONTROL Analysis Workspace] 中重新创建分段下拉菜单？**

[!UICONTROL Analysis Workspace] 中的下拉过滤器是一个灵活而强大的功能，可用来创建分段下拉菜单。在工作区项目中时：

1. 按住 ctrl 并单击 (Windows) 或按住 cmd 并单击 (Mac) 要包含在下拉菜单中的组件。不仅仅限于区段；任何组件都可以包含在下拉过渡器中。
2. 将组件组拖动到标有“在此处放置区段”的工作区区域。放手前，按住 Shift 键。

访问此[!UICONTROL 工作区]项目的用户现在可以使用此下拉菜单将区段或其他组件应用到该项目。有关更多信息，请参阅 Adobe Analytics 工具指南中的[面板概述](/help/analyze/analysis-workspace/c-panels/panels.md)。

**我习惯通过单击维度项目来查看深入信息。如何在 Analysis Workspace 中重现这种轻松的工作流？**

[!UICONTROL Analysis Workspace] 中的维度项目还具有一个轻松的划分工作流。使用右键单击（而不是左键单击）可访问该工作流。右键单击维度项目，单击 **“[!UICONTROL 划分]”，然后选择所需的组件。按住 Ctrl 并单击 (Windows) 或按住 Cmd 并单击 (Mac) 每个值，可将同一个划分应用于多个维度项目。
