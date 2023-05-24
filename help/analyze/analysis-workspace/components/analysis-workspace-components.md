---
description: Analysis Workspace 中的组件包括维度、指标、区段和日期范围，您可以将这些组件拖放到项目中。
title: 组件概述
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: 602f837689186f232c4c0f8baebbcf911446bc99
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 66%

---

# 组件概述

Analysis Workspace 中的组件包括维度、指标、区段和日期范围，您可以将这些组件拖放到项目中。

要访问“组件”菜单，请单击左边栏中的&#x200B;**[!UICONTROL 组件]**&#x200B;图标。您可以从左边栏在[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans)、[可视化图表](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hans)和组件之间切换，也可以使用[快捷键](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。

![](assets/component-overview.png)

您还可以转到&#x200B;**[!UICONTROL 项目 > 项目信息和设置 > 视图密度]**&#x200B;来调整项目的[视图密度设置](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hans)，以便在左边栏中一次查看更多值。

## 维度 {#dimensions}

[**维度**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html?lang=zh-Hans)是描述访客行为的文本属性，可以在分析中查看、细分和比较。它们可以在左侧的“组件”边栏（橙色部分）中找到，通常作为表中的行。

维度的示例包括[!UICONTROL 页面名称]、[!UICONTROL 营销渠道]、[!UICONTROL 设备类型]和[!UICONTROL 产品]。维度由 Adobe 提供，通过自定义实施来捕获（eVar、Prop、分类等）。

每个维度中还包含&#x200B;**维度项**。在左侧的“组件”边栏中，通过单击任意维度名称（黄色的项）旁边的右箭头可以找到维度项。

维度项的示例包括[!UICONTROL 主页]（在[!UICONTROL 页面] 维度中）、[!UICONTROL 付费搜索]（在[!UICONTROL 营销渠道]维度中）、[!UICONTROL 平板电脑]（在[!UICONTROL 移动设备类型]维度中）等等。

![](assets/dimensions.png)

## 指标 {#metrics}

[**指标**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html?lang=zh-Hans)是有关访客行为的量化指标。它们可以在左侧的“组件”边栏（绿色部分）中找到，通常作为表中的列。

指标的示例包括[!UICONTROL 页面查看数]、[!UICONTROL 访问]、[!UICONTROL 订单]、[!UICONTROL 平均用时]和[!UICONTROL 收入/订单]。指标由 Adobe 提供、通过自定义实施来捕获（[!UICONTROL 成功事件]）或者使用[计算指标生成器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=zh-Hans)创建。

![](assets/metrics.png)

## 区段 {#segments}

[**区段**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=zh-Hans)是应用到分析的受众过滤器。它们可以在左侧的“组件”边栏（蓝色部分）中找到，通常位于面板的顶部或者在表中指标列的上方。

区段的示例包括[!UICONTROL 移动设备访客]、[!UICONTROL 来自电子邮件的访问]和[!UICONTROL 经验证的点击]。区段由 Adobe 提供、在[面板拖放区域](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans)中创建或者使用[区段生成器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=zh-Hans)创建。

![](assets/segments.png)

## 日期范围 {#date-ranges}

[**日期范围**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html?lang=zh-Hans)是您进行分析时使用的日期的范围。它们可以在左侧的“组件”边栏（紫色部分）中找到，通常用于各个面板的日历中。

您可以使日期範圍元件相對於面板行事曆。 如需詳細資訊，請參閱 [關於相對面板日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates).

日期范围的示例包括 2019 年 7 月、[!UICONTROL 过去 4 周]和[!UICONTROL 本月]。日期范围由 Adobe 提供、在[面板日历](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans)中应用或者使用[日期范围生成器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=zh-Hans)创建。

![](assets/date-ranges.png)


## 管理元件 {#actions}

您可以直接在左側邊欄中管理元件。

1. 以滑鼠右鍵按一下元件。

   或

   選取元件，然後選取 **動作** 元件清單頂端的（3點）圖示。

   >[!TIP]
   >
   >   按住Shift鍵或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上）可選取多個元件。


   ![](assets/component-actions.png)

   | 元件動作 | 描述 |
   |--- |--- |
   | [!UICONTROL **标记**] | 通过对组件应用标记来组织或管理组件。然后，您可以通过单击过滤器或者键入 # 在左边栏中按标记搜索。标记在组件管理器中也可用作过滤器。 |
   | [!UICONTROL **收藏**] | 将组件添加到您的收藏夹列表中。与标记相似，您可在左边栏中按“收藏”进行搜索，然后在组件管理器中对其进行过滤。 |
   | [!UICONTROL **批准**] | 将组件标记为“已批准”可告知用户该组件得到了组织的批准。与标记相似，您可在左边栏中按“已批准”进行搜索，然后在组件管理器中对其进行过滤。 |
   | [!UICONTROL **共享**] | 将组件与组织中的用户共享。此选项仅对自定义组件可用，例如区段或计算指标。 |
   | [!UICONTROL **删除**] | 删除不再需要的组件。此选项仅对自定义组件可用，例如区段或计算指标。 |

自定义组件也可通过其相应的组件管理器进行管理。例如，[区段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)。

## 搜尋、篩選及排序元件清單

您可以在Analysis Workspace的左側邊欄中搜尋、篩選和排序元件清單，以快速找到特定元件。

### 搜尋元件清單

1. 選取 **元件** 圖示 ![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) 在左側邊欄中。

2. 在搜尋欄位中，開始輸入您要在專案中使用的元件名稱。

   元件型別可由顏色和圖示識別。 **Dimension** ![Dimension圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) 是橙色， **區段** ![「區段」圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 是藍色的， **日期範圍** ![日期範圍圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 是紫色的，並且 **量度** ![量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 是綠色的。 Adobe圖示會指出計算量度範本或區段範本，以及計算器圖示 ![計算器圖示](assets/calculated-metric-icon-created.png) 表示貴組織中Analytics管理員建立的計算量度。

3. 當元件出現在下拉式清單中時選取該元件。

### 篩選元件清單

{{release-limited-testing-section}}

1. 選取 **元件** 圖示 ![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) 在左側邊欄中。

2. 選取 **篩選** 圖示 ![資料字典篩選圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg).

   或

   在搜尋欄位中輸入井字型大小(#)。

3. 選取下列任一篩選選項來篩選元件清單：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **已批准**] | 仅显示标记为由管理员批准的组件。 |
   | [!UICONTROL **收藏夹**] | 仅显示收藏夹列表中的组件。有关将组件添加到收藏夹列表的信息，请参阅[组件概览](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。 |
   | [!UICONTROL **维度**] | 仅显示维度的组件。 |
   | [!UICONTROL **量度**] | 仅显示量度的组件。 |
   | [!UICONTROL **区段**] | 仅显示区段的组件。<!--this is Filters in CJA--> |
   | [!UICONTROL **日期范围**] | 仅显示日期范围的组件。 |
   | [!UICONTROL **显示所有**] | 显示所有组件。仅管理员有此选项可用。 |
   | [!UICONTROL **未批准**] | 仅显示未标记为由管理员批准的组件。作为管理员，这有助于确定需要您审阅和批准的组件。仅管理员有此选项可用。 |

4. （可選）若要進一步美化清單，您可以排序元件清單，如所述 [排序元件清單](#sort-the-component-list).

### 排序元件清單

1. （可選）將任何篩選器套用至元件清單，如所述 [篩選元件清單](#filter-the-component-list).

2. 選取 **元件** 圖示 ![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) 在左側邊欄中。

3. 選取 **排序** 圖示 ![排序元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選取下列任一篩選選項來排序元件清單：

   {{components-sort-options}}
