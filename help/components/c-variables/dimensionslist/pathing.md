---
description: 一组基于路径分析的报告。 从技术上讲，路径是指从一个页面名称移动到另一个页面名称（从一个值移动到另一个值）。
title: 路径分析
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 路径分析

一组基于路径分析的报告。 从技术上讲，路径是指从一个页面名称移动到另一个页面名称（从一个值移动到另一个值）。

请使用 [Analysis Workspace 流量](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/flow.html)了解更灵活的路径选项。

>[!NOTE] 要启用路径分析，请转到 **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**。 要在网站区域和服务器报表中启用路径分析，请联系客户关怀团队。

如果您需要了解收集值的顺序，则需要为收集这些值的变量启用路径。 页面的路径功能默认为启用。 默认情况下，路径不会为任何prop启用，因为它仅适用于某些情况。 联系客户关怀以启用prop上的路径分析。

>[!NOTE] 在 Ad Hoc Analysis 中，对某个 prop 启用分类时，路径量度将可用于为该启用 prop 设置的所有分类。

**示例——网站区域上的路径**

Enabling pathing for the *`s.channel`* variable allows you to track how site visitors move between Site Sections (as the value changes).

![](assets/path_sections.png)

路径随后可在各种路径报表中使用， [!UICONTROL Next Site Section Flow]例如显示访客在页面组或网站各部分中的移动方式。

![](assets/paths_report.png)

**示例——搜索路径**

从一个值到另一个值的相同概念也适用于其他流量变量，包括 *`s.props`*。 例如，如果为内部搜索词 *`s.prop`* 启用路径，则可以查看访客通过搜索词进行访问的路径。

**示例——每个登录状态的路径**

您可能希望了解人员如何根据访客的登录状态在您的站点中进行路径访问。 要查看此信息，您不会查看登录状态的路径报告，因为这些报告将显示访客如何更改该报告中的值，或者访客可能已从登录更改为注销。 而是将段值与变量连接 *`s.pageName`* 起来，然后路径到生成变量。 以下是每个成员状态的页面路径示例代码：

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

然后，启用路径查 *`s.prop19`* 看成员如何通过页面进行路径查看。

>[!NOTE] 如果您执行 Ad Hoc Analysis，则可以将页面路径分段，而无需关联区段值，然后对路径报表应用任何区段。

