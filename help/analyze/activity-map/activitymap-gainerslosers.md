---
description: 叠加图为您提供了多种配置数据可视化的方法，让您能够轻松地查看和了解页面上链接的受欢迎程度。
seo-description: 叠加图为您提供了多种配置数据可视化的方法，让您能够轻松地查看和了解页面上链接的受欢迎程度。
seo-title: 可自定义的叠加图
solution: Analytics
title: 可自定义的叠加图
topic: Activity Map
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# 可自定义的叠加图

叠加图为您提供了多种配置数据可视化的方法，让您能够轻松地查看和了解页面上链接的受欢迎程度。

叠加图让您能够直接在页面上看到单击数据。This is what separates a visual analysis tool like [!DNL Activity Map] from mostly tabular and graphical tools like Reports &amp; Analytics.

[!DNL Activity Map] 提供三种类型的叠加：

* 渐变叠加图（热图）
* 气泡叠加图
* 获胜方和失败方叠加图

您也可以配置[用于呈现动态内容的叠加图](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md)。

要更改叠加图，请打开[叠加图设置面板](/help/analyze/activity-map/activitymap-overlay-settings.md)，然后编辑可用的选项。

将鼠标悬停在叠加图上方时，可显示其[详细信息](/help/analyze/activity-map/activitymap-overlay-details.md)。

## Gradient overlay (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

使用渐变叠加图时，颜色浓度是根据链接的受欢迎程度而定。此颜色浓度可以被标准化为受欢迎程度的前 30 排名，或者行使绝对量度值的作用。

这些量度作为某种“热图”叠加在页面链接上，以回答各种关键问题，包括下列内容：

* 单个页面的值是什么？
* 页面上单个元素的值是什么？
* 页面上最有价值的“数字不动产”是什么？

![](assets/gradient.png)

## Bubble overlay {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

气泡叠加图可以在小型标注气泡中显示叠加内容（量度、百分比或排名）。

当您在工具栏的“叠加图类型”中选择这种叠加图时，就会出现气泡叠加图。Bubble overlays show for all links that match the selection in [[!DNL Activity Map] Settings](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, all...). 如果没有选择此选项，将会出现渐变叠加图。

![](assets/bubble_overlay.png)

>[!NOTE]
>
>子菜单的气泡叠加仅在显示子菜单时显示：
>
>![](assets/bubbles_submenu.png)&gt;

## Gainers and losers overlays {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL 获胜方和失败方叠加]** ，仅在“实时”模式下可用。 它们通过对比当前时段与上一时段的量度，报告链接活动的实时变化。它们能够为您提供一种直观且富有说服力的方式，让您实时查看变化趋势。

这种实时叠加图根据上一时段到当前时段所产生的量度值的变化，对点击情况进行排名。

![](assets/gainers_losers.png)

