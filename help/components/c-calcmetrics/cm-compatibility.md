---
description: 有关三个产品兼容性选项的说明。
title: 量度兼容性
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: d9f95b12a43305cecff1190e6544334f3b48835d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 68%

---

# 量度兼容性 {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="产品兼容性"
>abstract="&#39;少数可用的量度标准与有些 Adobe Analytics 工具不兼容。此列表中列出了与该度量兼容的工具。要使某个量度与所有 Adobe Analytics 工具兼容，请尝试编辑您的标准。"

本文介绍了三种产品兼容性选项。

在计算量度生成器中创建计算量度时，您的量度将显示为与Adobe Analytics中的一个或多个工具兼容。 例如Analysis Workspace、Reports &amp; Analytics、Data Warehouse。


| 兼容 | 描述 |
| --- | --- |
| 当前数据 | Adobe Analytics 中的[!UICONTROL 包括当前数据]选项让您可以查看最新的 Analytics 数据，通常在完全处理和完成某个数据时。[!UICONTROL 当前数据]显示几分钟内的大多数量度，提供可操作的数据用于快速决策。[!UICONTROL 当前数据]仅支持计算量度（包含乘法、除法、加法和减法）。[!UICONTROL 当前数据]不支持高级计算量度（包含区段或函数）。 |
| 完全处理数据 | 经过完全处理且包含区段和分类的数据。如果您要在完全处理数据之后查看所有量度，您可以通过从当前数据用户组中删除用户来禁用[!UICONTROL 当前数据]。 |
| 营销渠道报表 | 具有首次联系分配的量度仅与“营销渠道报表”兼容。 |
