---
description: Adobe Analysis Workspace 及其相关组件中的已知限制列表
title: Analysis Workspace 中的已知限制
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 100%

---

# Analysis Workspace 中的已知限制

以下是 Analysis Workspace 及其相关组件中的已知限制列表：

## 表格

* 将日期范围或量度用作表的行时，无法添加日期比较列。
* 当区段用作表的行时，将禁用通过所选内容创建量度。此外，通过所选内容创建量度不应应用于日期对齐列。
* 划分行的条件格式不能使用自定义范围。
* 当应用通过汇总行值设置来计算总数时（通常与静态行项目一起使用），表总行数不能趋势化。
* [!UICONTROL 贡献分析]只能在&#x200B;__[!UICONTROL 每日]粒度下运行。它不能针对[!UICONTROL 每小时]、[!UICONTROL 每周]等数据运行。

## 可视化图表

* 利用分段的可视化（如[!UICONTROL 流失]、[!UICONTROL 流量]、[!UICONTROL 同类群组]和[!UICONTROL 直方图]）不能接受计算量度作为输入。
* [!UICONTROL 流量]：登入/退出维度（例如，[!UICONTROL 进入页面]）不能在流量中使用。
* [!UICONTROL 同类群组]：非整数不能用作同类群组标准。

## 面板

* 区段比较：如果在初始放置区中使用区段模板，则不会创建[!UICONTROL 其他各项]区段。

## “组件”>“区段”

* 某些量度和维度不可分段，如[!UICONTROL 发生次数]、[!UICONTROL 唯一访客]，等等。
* 在[面板放置区](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans)中创建的临时区段是一种快速过滤器。除非公开这些区段，否则它们不会出现在 Workspace 的左边栏或区段组件管理器中。有关更多信息，请参阅[快速区段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)。

## “组件”>“计算量度”

* 计算量度不能用于某些可视化图表。请参阅上面的“可视化”。
* 计算量度无法在[!UICONTROL 归因]面板中使用，因为计算量度本身可以包括单独的归因模型。
* 如果从工作区中创建计算量度（而不是从[!UICONTROL 组件 > 区段]创建），则某些组件和操作符将不可用。例如，[!UICONTROL IP 地址]。

## “组件”>“日期范围”

* 自定义日期范围不支持[!UICONTROL 去年今日]、[!UICONTROL 上个月今日]，等等。

## “组件”>“虚拟报表包”

* 启用报表时间处理后，某些组件将不受支持。有关完整列表，请参阅[报表时间处理](/help/components/vrs/vrs-report-time-processing.md)。

## 组件 > 所有组件 > 报表设置

* [!UICONTROL 报表设置]页面上的某些设置不适用。Analysis Workspace 只使用底部的[!UICONTROL 语言/货币/编码]设置：[!UICONTROL 千位分隔符]、[!UICONTROL 计划报表编码]和 [!UICONTROL CSV 分隔符]。

## 归因

* [!UICONTROL 归因]中不支持量度的子集。有关完整列表，请参阅[归因常见问题解答](/help/analyze/analysis-workspace/attribution/faq.md)。
