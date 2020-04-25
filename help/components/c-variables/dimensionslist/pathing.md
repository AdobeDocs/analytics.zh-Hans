---
description: 一组基于路径分析的报表。从技术上说，路径分析意味着从一个页面名称进入另一个页面名称（从一个值到另一个值）。
title: 路径分析
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 路径分析

一组基于路径分析的报表。从技术上说，路径分析意味着从一个页面名称进入另一个页面名称（从一个值到另一个值）。

请使用 [Analysis Workspace 流量](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/flow.html)了解更灵活的路径选项。

>[!NOTE]要启用路径分析，请转到&#x200B;**[!UICONTROL 管理员 > 报表包 > 编辑设置 > 流量 > 流量变量]**。要在网站区域和服务器报表中启用路径分析，请联系客户关怀团队。

如果您要了解值收集的顺序，则需为搜集这些值的变量启用路径。页面默认启用路径。路径在默认情况下没有对任何 prop 启用，因为它仅适合特定情况。请与客户关怀联系以对 prop 启用路径。

>[!NOTE] 在 Ad Hoc Analysis 中，对某个 prop 启用分类时，路径量度将可用于为该启用 prop 设置的所有分类。

**示例 - 网站区域路径**

对 *`s.channel`* 变量启用路径，使您可以对网站访客如何在网站区域之间移动（随着值的变化）进行跟踪。

![](assets/path_sections.png)

之后，路径即可在多种路径报表中使用，例如显示访客是如何在页面群组或网站区域间移动的[!UICONTROL 下一网站区域流量]报表。

![](assets/paths_report.png)

**示例 - 搜索路径**

从一个值移动到另一个值的概念同样也适用于其他流量变量，包括 *`s.props`*。例如，如果为内部搜索词 *`s.prop`* 启用路径，则可以查看访客通过搜索词进行访问的路径。

**示例 - 按登录状态分析路径**

您可能希望根据访客的登录状态来了解访客访问您网站的路径。若要查看此信息，您无需查看登录状态的路径分析报表，因为它们会向您显示访客是如何更改该报表中的值，或者访客是如何从登录状态更改为注销状态。相反，使用 *`s.pageName`* 变量关联分段值，然后对该结果变量进行路径分析。以下是按成员状态进行页面路径分析的示例代码：

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

然后，对 *`s.prop19`* 启用路径，以了解成员访问页面的路径。

>[!NOTE] 如果您执行 Ad Hoc Analysis，则可以将页面路径分段，而无需关联区段值，然后对路径报表应用任何区段。

