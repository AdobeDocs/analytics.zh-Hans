---
title: Workspace中的多个报表包
description: 了解如何在Workspace中使用多个报表包创建项目以及创建原因
translation-type: tm+mt
source-git-commit: 48b0d6a92de1697acc54c8601e6b2c920e01ffee

---


# Workspace中的多个报表包

>[!IMPORTANT]
>此功能目前处于测试阶段，将于2020年初发布。

您现在可以在Analysis Workspace中使用来自多个报表包的数据创建项目。 现在在面板级别上选择了报表包，因此您可以为同一Workspace项目中的每个面板选择不同的报表包。

例如，如果您希望

* 比较两个不同区域的数据，数据驻留在两个不同的报表包中。 您可以构建表和可视化以并排比较数据。

* 构建指标和可视化仪表板，向其他组织报告。 您现在可以将不同报表包中的数据拉入同一项目。

## 活动面板

我们在此功能中引入了“活动面板”与“非活动面板”的概念。 活动面板周围的浅蓝色边框可以识别。 只需在面板内单击，该面板便成为活动面板。

>[!IMPORTANT]
>即使其他面板具有相同 **的报表包**，也只能将组件拖放到活动面板中。 如果要在拖放时更改面板，可以使用短剪切：拖动 `shift` 时按键可将非活动面板更改为活动面板。

| 任务 | 活动面板 | 非活动面板 |
|---|---|---|
| 更改报告套件 | 是 | 否 |
| 拖放组件 | 是 | 否 |
| 拖放可视化 | 是 | 否 |

## 使用多个报表包

![](assets/mrs-ui.png)

1. 在Workspace中使用2个或更多面板创建新项目。

1. 将组件（度量、维度、区段、日期范围）拖放到面板中。 确保面板具有特定于其报表包的数据和可视化。


   >[!NOTE]
   >有时，在加载项目（或切换到报表包）时，“不兼容的报表包”消息会显示，其中并非项目中包含的所有组件都包含在报表包中。 将列出缺少的组件。 按照 [这些说明](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles) ，将权限设置为所需的量度／维度。

   ![](assets/incompat-rs.png)

   您有3种方法可处理此不兼容问题：
   * 继续处理某些缺少的组件。 这将导致这些组件没有数据和／或空白可视化。
   * 撤消.
   * 更改报表包.

1. 将面板更改为其他报表包，并注意组件标签（当前活动的报表包）和列出的组件如何根据新的报表包进行更新。

1. 使用键盘快捷键(`shift` 拖动时)将非活动面板转换为活动面板。

1. （可选）您还可以转到其他Analytics组件构建器，并确保它们现在显示一个报表包标签，指示

   * 将创建区段的位置：区 [段构建器](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html)。
   * 创建计算量度的位置：计 [算量度生成器](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)。
   * 将生成警报的位置：警 [报生成器](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html)。