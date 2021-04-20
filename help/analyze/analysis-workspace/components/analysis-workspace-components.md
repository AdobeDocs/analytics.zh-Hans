---
description: 'Analysis Workspace中的组件包括可拖放到项目上的维度、量度、区段和日期范围。 '
title: 组件概述
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 17%

---


# 组件概述

Analysis Workspace中的组件包括可拖放到项目上的维度、量度、区段和日期范围。

要访问“组件”菜单，请单击左边栏中的&#x200B;**[!UICONTROL 组件]**&#x200B;图标。 您可以在左边栏图标中的[面板](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/panels/panels.html)、[可视化](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)和组件之间切换，或使用[热键](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。

![](assets/component-overview.png)

您还可以通过转到&#x200B;**[!UICONTROL “项目”>“项目信息和设置”>“视图密度”]**，调整项目的[视图密度设置](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)，以同时在左边栏中查看更多值。

## 维度{#dimensions}

[**维**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) 共享描述您的访客行为的文本属性，可在分析中查看、划分和比较。它们位于左边的“组件”边栏（橙色部分）中，通常作为表的行应用。

维的示例包括[!UICONTROL 页面名称]、[!UICONTROL 营销渠道]、[!UICONTROL 设备类型]和[!UICONTROL 产品]。 Dimension由Adobe提供，并通过您的自定义实施(eVar、属性、分类等)来捕获。

每个维中还包含&#x200B;**维度项**。 Dimension项可在左侧的组件边栏中单击任何维度名称旁边的向右箭头（项目为黄色）。

维项目的示例包括[!UICONTROL Homepage]（在[!UICONTROL Page]维中）、[!UICONTROL 付费搜索](在[!UICONTROL 营销渠道]维中)、[!UICONTROL Tablet]（在[!UICONTROL 移动设备类型中）a11/>维度)，依此类推。]

![](assets/dimensions.png)

## 指标 {#metrics}

[**量**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) 度是有关访客行为的量度。它们位于左侧的组件边栏（绿色部分）中，通常作为表的列应用。

量度示例包括[!UICONTROL 页面视图]、[!UICONTROL 访问]、[!UICONTROL 订单]、[!UICONTROL 平均逗留时间]和[!UICONTROL 收入/订单]。 量度由Adobe提供，或通过您的自定义实现([!UICONTROL 成功事件])捕获，或使用[计算量度生成器](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)创建。

![](assets/metrics.png)

## 区段 {#segments}

[**段**](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) 是应用于您的受众的过滤器。它们位于左侧的组件边栏（蓝色部分）中，通常应用于面板顶部或表格中量度列上方。

区段示例包括[!UICONTROL 移动设备访客]、[!UICONTROL 电子邮件访问]和[!UICONTROL 已验证点击]。 区段由Adobe提供，或在[面板拖放区](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)中创建，或使用[区段生成器](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/segmentation-workflow/seg-build.html)创建。

![](assets/segments.png)

## 日期范围 {#date-ranges}

[**日**](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) 期范围是您进行分析的日期范围。它们位于左侧的“组件”边栏（紫色部分）中，通常应用于每个面板的日历。

日期范围的例子包括2019年7月、[!UICONTROL 最近4周]和[!UICONTROL 本月]。 日期范围由Adobe提供，应用在[面板日历](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)中，或使用[日期范围生成器](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)创建。

![](assets/date-ranges.png)

## 组件操作 {#actions}

您可以直接在左边栏中管理组件（单独或通过选择多个组件）。 右键单击组件或单击组件列表顶部的操作点图标。

![](assets/component-actions.png)

| 组件操作 | 描述 |
|--- |--- |
| 标记 | 通过对组件应用标记来组织或管理组件。然后，单击过滤器或键入#，即可按左边栏中的标记进行搜索。 标签还在组件管理器中充当过滤器。 |
| 收藏 | 将组件添加到您的收藏夹列表中。与标记一样，您可以在左边栏中按收藏夹进行搜索，并在组件管理器中按它们进行筛选。 |
| 批准 | 将组件标记为已批准，以向用户发出该组件已组织批准的信号。 与标记类似，您可以在左边栏中按“已批准”搜索，并在组件管理器中按它们进行筛选。 |
| 共享 | 将组件共享给组织中的用户。 此选项仅对自定义组件（如区段或计算量度）可用。 |
| 删除 | 删除不再需要的组件。 此选项仅对自定义组件（如区段或计算量度）可用。 |

自定义组件还可以通过各自的组件管理器进行管理。 例如，[区段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)。
