---
title: 子点击分析
description: 了解子点击分析如何让您在Adobe Analytics中筛选点击中的各个产品，消除产品报表中的归因出血。
feature: Segmentation
hide: true
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: f56d4b675d55608d4049fcebaf2de549aca40a5c
workflow-type: tm+mt
source-wordcount: 808
ht-degree: 0%

---

# 子点击分析

通过子点击分析，可在比点击级别更精细的级别分析产品数据。 您可以对点击中的单个产品进行分段，而不是对整个点击进行过滤。 例如，按特定产品类别进行分段，而不包括同一订单中购买的所有其他产品。


在Adobe Analytics中，[Products变量](/help/components/dimensions/product.md)可以在一次点击中捕获多个产品。 如果没有子点击分析，对产品属性进行分段将返回点击中的任何产品与产品属性匹配的所有点击。 结果是不正确的归因和夸大的收入量度。 子点击分析可将过滤器范围设置为点击中的单个产品行，并解决这些问题。

在子点击分析中，排除逻辑的行为与针对Products变量的标准点击级别排除有所不同。 当您排除[!UICONTROL 产品]容器中的产品属性时，区段会返回&#x200B;**具有产品**&#x200B;但不匹配排除条件的点击。 该区段不会返回完全没有产品的点击。

## 示例

您只想从“男性”类别中测量在线收入。 如果没有子点击分析，则应用Men区段将包括来自任何订单（点击）上的每个产品的收入，该订单至少包含一个具有Men类别的产品。 利用子点击分析，可将过滤器范围缩小到产品级别，并仅返回Men类别产品的收入。

您还需要测量除Men类别之外的所有其他类别的在线收入。

>[!BEGINTABS]

>[!TAB 点击分析]

在分段生成器中，或作为&#x200B;**[!UICONTROL 快速区段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 点击数]**&#x200B;容器中&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL 零售业：时尚产品类别]** **[!UICONTROL 等于]** **[!UICONTROL 男性]**。

![显示产品类别为“男性”的点击级别分段的面板](./assets/product-category-segmentation-hits.png)

因此，至少包含一个&#x200B;**[!UICONTROL 男性]** **[!UICONTROL 零售：时尚产品类别]**&#x200B;的所有订单都将被考虑，并且这些订单中来自其他产品的收入包含在&#x200B;**[!UICONTROL 在线收入]**量度中。
当您报告类别时，报告了**[!UICONTROL 零售业：时装产品类别]**&#x200B;的所有其他值，这些值属于包含&#x200B;**[!UICONTROL 男士]** **[!UICONTROL 零售业：时装产品类别]**&#x200B;的产品的订单。

>[!TAB 子点击分析]

在分段生成器中，或作为&#x200B;**[!UICONTROL 快速区段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 产品]**&#x200B;容器中&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL 零售业：时尚产品类别]** **[!UICONTROL 等于]** **[!UICONTROL 男性]**。

![显示产品类别Men的子点击级别分段的面板](./assets/product-category-segmentation-sub-hits.png)

因此，至少包含&#x200B;**[!UICONTROL 男性]** **[!UICONTROL 零售：时装产品类别]**&#x200B;的所有订单都被考虑在内，并且在&#x200B;**[!UICONTROL 在线收入]**&#x200B;量度中只包含属于&#x200B;**[!UICONTROL 男性]** **[!UICONTROL 零售：时装产品类别]**的产品收入。
当您报告类别时，仅报告**[!UICONTROL 男性]** **[!UICONTROL 零售：时尚产品类别]**。

>[!TAB 子点击分析（排除）]

在分段生成器中，或作为&#x200B;**[!UICONTROL 快速区段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 产品]**&#x200B;容器中&#x200B;**[!UICONTROL 排除]** **[!UICONTROL Dimension]** **[!UICONTROL 零售业：时尚产品类别]** **[!UICONTROL 等于]** **[!UICONTROL 男性]**。

![显示子点击级别的分段以排除产品类别门槛的面板](./assets/product-category-segmentation-sub-hits-exclude.png)

要在产品级别排除，将包含至少包含一个产品的点击，然后在该范围内应用子点击级别的排除。 此排除项与点击级别的排除项不同，点击级别的排除项会排除整个点击。

>[!ENDTABS]

在Adobe Analytics中，子点击分析特别适用于&#x200B;**[!UICONTROL Products]**&#x200B;变量。 **[!UICONTROL Products]**&#x200B;变量是Adobe Analytics中唯一支持子点击分析的多值对象。


>[!WARNING]
>
>发布此功能时，以下章节将移至其相关文章（关于区段生成器、快速区段、直方图等）。 然后，这些文章将参考本文以供有关什么是子点击分析的参考。 当前未执行此操作，以免在功能不可用时让客户感到困惑。

## 容器自动推理

将产品维度或量度拖入区段生成器或快速区段面板时，系统自动选择&#x200B;**[!UICONTROL 产品]**&#x200B;容器，而不使用默认的&#x200B;**[!UICONTROL 点击]**&#x200B;容器。 此行为将区段的范围限制为单个产品，而不是整个点击。

## 混合容器行为

如果将产品级组件和点击级组件拖入单个区段规则，则系统将使用&#x200B;**[!UICONTROL 点击]**&#x200B;容器，该容器是最高（粒度最小）的共享容器。 如果属于区段规则的所有组件都是产品级别的，则使用&#x200B;**[!UICONTROL Product]**&#x200B;容器。

## 左边栏中的产品过滤器

区段生成器的左边栏中包含一个新的过滤器选项，可仅显示产品维度和量度。 这使得在构建子点击区段时更容易查找产品级组件。

>[!NOTE]
>
>此筛选器选项仅在区段生成器中可用。 它在其他左边栏（如Analysis Workspace面板或可视化图表）中不可用。

## 直方图可视化图表

直方图可视化包括一个新的子点击容器下拉菜单。 这使您可以在产品级别存储量度值。 例如，计算每个订单而不是每次点击的产品发生次数。

直方图是唯一需要选择子点击容器可视化。 所有其他面板和可视化图表无需额外配置即可使用子点击分析数据。
