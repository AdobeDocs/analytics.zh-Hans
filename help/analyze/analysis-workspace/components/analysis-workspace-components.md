---
description: 'Analysis Workspace 中的组件包括维度、量度、区段和日期范围，您可以将这些组件拖放到项目中。 '
title: 组件概述
feature: Workspace 基础知识
role: Business Practitioner, Administrator
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 92%

---

# 组件概述

Analysis Workspace 中的组件包括维度、量度、区段和日期范围，您可以将这些组件拖放到项目中。

要访问“组件”菜单，请单击左边栏中的&#x200B;**[!UICONTROL 组件]**&#x200B;图标。您可以从左边栏在[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans)、[可视化图表](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hans)和组件之间切换，也可以使用[快捷键](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。

![](assets/component-overview.png)

您还可以转到&#x200B;**[!UICONTROL 项目 > 项目信息和设置 > 视图密度]**&#x200B;来调整项目的[视图密度设置](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hans)，以便在左边栏中一次查看更多值。

## 维度 {#dimensions}

[**维度**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html)是描述访客行为的文本属性，可以在分析中查看、细分和比较。它们可以在左侧的“组件”边栏（橙色部分）中找到，通常作为表中的行。

维度的示例包括[!UICONTROL 页面名称]、[!UICONTROL 营销渠道]、[!UICONTROL 设备类型]和[!UICONTROL 产品]。维度由 Adobe 提供，通过自定义实施来捕获（eVar、Prop、分类等）。

每个维度中还包含&#x200B;**维度项**。在左侧的“组件”边栏中，通过单击任意维度名称（黄色的项）旁边的右箭头可以找到维度项。

维度项的示例包括[!UICONTROL 主页]（在[!UICONTROL 页面] 维度中）、[!UICONTROL 付费搜索]（在[!UICONTROL 营销渠道]维度中）、[!UICONTROL 平板电脑]（在[!UICONTROL 移动设备类型]维度中）等等。

![](assets/dimensions.png)

## 量度 {#metrics}

[**量度**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html)是有关访客行为的量化指标。它们可以在左侧的“组件”边栏（绿色部分）中找到，通常作为表中的列。

量度的示例包括[!UICONTROL 页面查看数]、[!UICONTROL 访问]、[!UICONTROL 订单]、[!UICONTROL 平均用时]和[!UICONTROL 收入/订单]。量度由 Adobe 提供、通过自定义实施来捕获（[!UICONTROL 成功事件]）或者使用[计算量度生成器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)创建。

![](assets/metrics.png)

## 区段 {#segments}

[**区段**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)是应用到分析的受众过滤器。它们可以在左侧的“组件”边栏（蓝色部分）中找到，通常位于面板的顶部或者在表中量度列的上方。

区段的示例包括[!UICONTROL 移动设备访客]、[!UICONTROL 来自电子邮件的访问]和[!UICONTROL 经验证的点击]。区段由 Adobe 提供、在[面板拖放区域](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)中创建或者使用[区段生成器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html)创建。

![](assets/segments.png)

## 日期范围 {#date-ranges}

[**日期范围**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)是您进行分析时使用的日期的范围。它们可以在左侧的“组件”边栏（紫色部分）中找到，通常用于各个面板的日历中。

日期范围的示例包括 2019 年 7 月、[!UICONTROL 过去 4 周]和[!UICONTROL 本月]。日期范围由 Adobe 提供、在[面板日历](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)中应用或者使用[日期范围生成器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)创建。

![](assets/date-ranges.png)

## 组件操作 {#actions}

您可以在左边栏中直接管理组件（分别管理或者一次选择多个）。右键单击某个组件或者单击组件列表顶部的“操作”点图标。

![](assets/component-actions.png)

| 组件操作 | 描述 |
|--- |--- |
| 标记 | 通过对组件应用标记来组织或管理组件。然后，您可以通过单击过滤器或者键入 # 在左边栏中按标记搜索。标记在组件管理器中也可用作过滤器。 |
| 收藏 | 将组件添加到您的收藏夹列表中。与标记相似，您可在左边栏中按“收藏”进行搜索，然后在组件管理器中对其进行过滤。 |
| 批准 | 将组件标记为“已批准”可告知用户该组件得到了组织的批准。与标记相似，您可在左边栏中按“已批准”进行搜索，然后在组件管理器中对其进行过滤。 |
| 共享 | 将组件与组织中的用户共享。此选项仅对自定义组件可用，例如区段或计算量度。 |
| 删除 | 删除不再需要的组件。此选项仅对自定义组件可用，例如区段或计算量度。 |

自定义组件也可通过其相应的组件管理器进行管理。例如，[区段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)。
