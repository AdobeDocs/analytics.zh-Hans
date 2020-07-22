---
title: 常见问题解答
description: 获取从第三方平台转到 Adobe 时的常见问题解答。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 66%

---


# 常见问题解答

**如何将历史数据从第三方平台迁移到AdobeAnalytics?**

每个 Analytics 平台都有不同的数据收集、处理和存储方式。Adobe 建议建立明确的截止日期，以便开始在 Adobe Analytics 中收集和使用数据，而不是迁移历史数据。经常使用的截止日期是财政年度的开始、日历年的开始或日历月的开始。如果用户希望查看历史数据，则可登录第三方平台以获取任何特定的历史报告需求。

如果贵组织坚决要求将历史数据迁移到 Adobe，请与贵组织的客户经理联系。实施顾问可以与您的组织合作，将 Google Analytics 数据导出转换为可由 Adobe 数据收集服务器引入的数据源。

Adobe 不建议迁移历史数据，因为这是一个复杂的过程，而且对组织而方，成本过于高昂。访客身份识别也无法无缝地迁移到 Adobe，因为这两个平台中的访客信息以不同的格式存储在不同的 Cookie 中。

**我习惯了使用许多报表中的分段下拉菜单。How can I recreate that in[!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. 在工作区项目中时：

1. 按住 ctrl 并单击 (Windows) 或按住 cmd 并单击 (Mac) 要包含在下拉菜单中的组件。不仅仅限于区段；任何组件都可以包含在下拉过渡器中。
2. 将组件组拖动到标有“在此处放置区段”的工作区区域。放手前，按住 Shift 键。

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**我习惯单击维度项目以查看追溯。 如何在 Analysis Workspace 中重现这种轻松的工作流？**

Analysis Workspace中的 [!UICONTROL 维] 项目也具有简单的细分工作流。 使用右键（而非左键）访问它。 Right-click on a dimension item, click **[!UICONTROL Breakdown], then select the desired component. 对每个值使用ctrl+单击(Windows)或cmd+单击(Mac)，可将同一细分应用于多个维项目。
