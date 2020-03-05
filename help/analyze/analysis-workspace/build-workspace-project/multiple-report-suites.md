---
title: 工作区中的多个报表包
description: 了解如何在工作区中使用多个报表包来创建项目以及为什么创建项目
translation-type: tm+mt
source-git-commit: e60de040e1036a1344baecfcc9c1fd5d71c4cf40

---


# 工作区中的多个报表包

您现在可以在 Analysis Workspace 中使用多个报表包的数据创建项目。现在可以在面板级别选择报表包，因此您可以在同一工作区项目中为每个面板选择不同的报表包。

例如，如果您想要

* 比较两个不同区域的数据，以及存储在两个不同的报表包中的数据。您可以构建一些表格和可视化图表，以并排比较数据。

* 构建一个包含量度和可视化图表的功能板，向其他组织报告。您现在可以将不同报表包中的数据提取到同一项目。

## 活动面板

我们在这项功能中引入了“活动面板”与“非活动面板”的概念。您可以通过周围的浅蓝色边框识别活动面板。 只需在面板内单击即可将该面板转换为活动面板。

>[!IMPORTANT]
>您可以拖放到与活动面板位于同一报告套件中的任何面板。 通过拖入同一报告包的非活动面板，该面板将变为活动面板。

| 任务 | 活动面板 | 非活动面板 |
|---|---|---|
| 更改报表包 | 是 | 否 |
| 拖放组件 | 是 | 是，适用于与活动面板位于同一报告套件中的任何面板。 |
| 拖放可视化图表 | 是 | 是，适用于与活动面板位于同一报告套件中的任何面板。 |

## 使用多个报表包

![](assets/mrs-ui.png)

1. 在工作区中创建具有 2 个或更多面板的新项目。

1. 将组件（量度、维度、区段、日期范围）拖放到面板中。确保面板具有特定于其报表包的数据和可视化图表。


   >[!NOTE]
   >有时，在加载项目（或切换到报表包）时，不会显示横幅，其中项目中包含的所有组件都包含在报表包中。 系统将会列出缺少的组件。按照[这些说明](/help/admin/admin-console/permissions/product-profile.md)，设置所需量度/维度的权限。

   ![](assets/incompat-rs.png)

   您有 3 个选项可处理这种不兼容的问题：
   * 启用所需的维度／指标
   * 更改报表包。
   * 继续保持缺少一些组件的状态。此操作将导致没有关于这些组件的数据和/或可视化图表显示空白。

1. 将面板更改为其他报表包，并注意组件标签（当前为活动的报表包）和列出的组件如何根据新的报表包进行更新。

1. Use a keyboard shortcut (`shift` while dragging) to turn an inactive panel to an active panel.

1. （可选）您还可以转到其他 Analytics 组件生成器，并确保它们现在显示一个报表包标签，指示

   * 将创建区段的位置：[区段生成器](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html)。
   * 将创建计算量度的位置：[计算量度生成器](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)。
   * 将生成警报的位置：[警报生成器](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html)。