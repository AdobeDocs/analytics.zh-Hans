---
description: 'Analysis Workspace地区的组件由维度、指标、细分和日期范围组成，您可以将它们拖放到项目中。 '
title: 组件概述
translation-type: tm+mt
source-git-commit: 459d650b30355912f4c9195c05da6728610109e8
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 13%

---


# 组件概述

Analysis Workspace地区的组件由维度、指标、细分和日期范围组成，您可以将它们拖放到项目中。

To access the Components menu, click the **[!UICONTROL Components]** icon in the left rail. 您可以从左边栏 [图标](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)，或通过使 [用热键](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)，在“面板”、“可视化”和“组件”之间 [切换](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。

![](assets/component-overview.png)

您还可以通过转到 [“项目”](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) >“项目信息和设置”>“视图密度” **[!UICONTROL ，一次调整项目的视图密度设置，以在左边栏]**&#x200B;中查看更多值。

## 维度 {#dimensions}

[**Dimension**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) 是描述访客行为的文本属性，可以在分析中查看、细分和比较。 它们可在左边的组件边栏（橙色部分）中找到，通常作为表的行应用。

维的示例包括 [!UICONTROL 页面名称]、 [!UICONTROL 营销]渠道 [!UICONTROL 、设]备类型 和产品。 Dimension由Adobe提供，并通过您的自定义实施(eVar、Prop、分类等)进行捕获。

每个维中还 **包含维** 项。 Dimension项可在左侧组件边栏中单击任何维名称旁边的向右箭头（项目为黄色）。

维项目的示例包 [!UICONTROL 括主页] (在页面维 [!UICONTROL 中] )、付 [!UICONTROL 费搜索] (在营销维中 [!UICONTROL )、渠道(在中] )、（在Device Mobile Dimension中），等等。

![](assets/dimensions.png)

## 量度 {#metrics}

[**指标**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) 是关于访客行为的量化指标。 它们位于左侧的组件边栏（绿色部分）中，通常作为表的列应用。

指标的示例包括 [!UICONTROL 页面视图]、 [!UICONTROL 访问]、 [!UICONTROL 订单]、平 [!UICONTROL 均花费时间、]、收入／订单收入。 量度由Adobe提供，或通过自定义实施(成[!UICONTROL 功事件])捕获，或使用“计算量度 [生成器”创建](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)。

![](assets/metrics.png)

## 区段 {#segments}

[**区段**](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) 是应用于您的受众的过滤器。 它们可在左边的组件边栏（蓝色部分）中找到，通常应用于面板顶部或表格中的度量列上方。

区段的示例包 [!UICONTROL 括移动设备访客]、 [!UICONTROL 电子邮件访问]和经过 [!UICONTROL 身份验证的点击]。 区段由Adobe提供，或在面板拖放区 [域创建](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)，或使用区段构 [建器创建](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/segmentation-workflow/seg-build.html)。

![](assets/segments.png)

## 日期范围 {#date-ranges}

[**日期范围**](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) 是您进行分析的日期范围。 它们位于左侧的组件边栏（紫色部分）中，通常应用于每个面板的日历。

日期范围的示例包括2019年7 [!UICONTROL 月、最近]4周 [!UICONTROL 和本月]。 日期范围由Adobe提供、应用于面 [板日历](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)，或使用日期范 [围生成器创建](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)。

![](assets/date-ranges.png)

## 组件操作 {#actions}

您可以直接在左边栏中管理组件（单独或通过选择多个组件）。 右键单击某个组件或单击组件列表顶部的操作点图标。

![](assets/component-actions.png)

| 组件操作 | 描述 |
|--- |--- |
| 标记 | 通过对组件应用标记来组织或管理组件。然后，您可以单击过滤器或键入#，按左边栏中的标记进行搜索。 标记还在组件管理器中充当过滤器。 |
| 收藏 | 将组件添加到您的收藏夹列表中。与标记一样，您可以按左边栏中的收藏夹进行搜索，并在组件管理器中按它们进行筛选。 |
| 批准 | 将组件标记为“已批准”，以向用户发出组织批准的信号。 与标记类似，您可以在左边栏中按“已批准”搜索，并在组件管理器中按它们进行筛选。 |
| 共享 | 将组件共享给组织中的用户。 此选项仅对自定义组件可用，如区段或计算量度。 |
| 删除 | 删除不再需要的组件。 此选项仅对自定义组件可用，如区段或计算量度。 |

自定义组件还可以通过各自的组件管理器进行管理。 例如，区段 [管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)。
