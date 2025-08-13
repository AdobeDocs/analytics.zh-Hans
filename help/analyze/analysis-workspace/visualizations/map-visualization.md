---
description: 使用地图可视化图表在地理地图可视化图表上绘制数据。
title: 地图
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: aad8c1ba3c76cd35aa37a155102b5fd6b4b7ca27
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 96%

---

# 地图 {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="地图"
>abstract="这种可视化图表通过在地图中叠加量度来表示。这种可视化图表对于识别不同地理区域的数据非常有用。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="气泡"
>abstract="使用气泡绘制事件地图。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="热图"
>abstract="使用热图绘制事件地图。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的地图可视化图表。_<br/>_查看本文的[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/visualizations/map)CustomerJourneyAnalytics_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg)版本的&#x200B;_&#x200B;**映射**。_

>[!ENDSHADEBOX]



Analysis Workspace 中的![全球](/help/assets/icons/Globe.svg)**[!UICONTROL 地图]**&#x200B;可视化图表

* 允许您生成任何量度（包括计算量度）的可视地图，
* 用于识别和比较不同地理区域间的量度数据，
* 可以支持两种数据源：出自移动设备使用情况的经纬度或 Web 使用情况的地理维度，
* 支持 PDF 导出，以及
* 利用 WebGL 显示图形。如果您的图形驱动程序不支持 WebGL 渲染，则可能需要更新您的驱动程序。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的地图可视化图表](https://video.tv.adobe.com/v/41507/?quality=12&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


## 使用

1. 添加![地图](/help/assets/icons/Globe.svg) [!UICONTROL 地图]可视化图表。请参阅[将可视化图表添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。您只能将地图可视化图表拖到自由格式表的顶部。

   ![地图配置](assets/map-configuration.png){width="50%"} -

1. 从下拉列表中选择量度。或从量度列表中拖入一个量度（包括计算量度）。
1. 指定要从中提取内容的数据源。只有在为移动应用程序数据启用了位置跟踪时，才会显示此对话框。

   | 来源 | 描述 |
   | --- | --- |
   | **[!UICONTROL 移动设备经纬度]** | 此选项表示移动应用程序数据。 只有在通过 [!UICONTROL Analytics] > [!UICONTROL 管理员] > [!UICONTROL 报告包] >（选择报告包）> [!UICONTROL 编辑设置] > [!UICONTROL 移动设备管理] > [!UICONTROL 启用位置跟踪]为报告包启用该设置时，才会看到此选项。 这个设置是默认的（如果已启用位置跟踪）。 |
   | **[!UICONTROL 地理维度]** | 此选项表示有关访客位置（基于访客的 IP 地址）的按地理位置分段的数据。 此数据将被转换为[!UICONTROL 国家]、[!UICONTROL 地区]和[!UICONTROL 城市]。 请注意，它不会转到 DMA 或邮政编码级别。 几乎所有报告包都启用了此维度。如果您的报告包还没有启用此维度，请联系 Adobe 客户关怀以启用地理报告。 |

1. 选择&#x200B;**[!UICONTROL 生成]**。

   生成了带有气泡的世界地图可视化图表。

   ![](assets/bubble-world-view.png)

1. 您现在可以：

   * 通过双击地图或使用滚轮，**放大**&#x200B;此地图以放大特定区域。地图根据光标的放置位置进行相应的缩放。通过缩放交互，所需的维度（国家/地区 > 州 > 城市）将会根据缩放级别自动更新。
   * 通过并排放置地图可视化图表，**比较**&#x200B;同一项目中的两个或更多地图可视化图表。
   * **显示同期（例如，年度）比较信息**：

      * 显示负数：例如，如果您绘制的是年度同比量度，地图会在纽约上方显示 -33%。
      * 对于&#x200B;*百分比*&#x200B;类型的量度，进行聚类分析时会将百分比平均起来计算。
      * 绿/红颜色方案：正/负

   * 通过按住 [!UICONTROL Ctrl] 键并移动地图，**旋转** 2D 或 3D 地图。

   * 使用以下描述的[设置](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E)，**切换**&#x200B;到其他视图，如热图。请注意，气泡视图是默认设置。

1. **保存**&#x200B;该项目，以保存所有地图设置（坐标、缩放、旋转）。
1. 通过从左边栏拖入位置维度和量度，填充可视化图表下方的自由格式表。



## 配置

要重新配置地图可视化图表，请选择![编辑](/help/assets/icons/Edit.svg)。


## 设置

要定义可视化图表的设置，请选择![设置](/help/assets/icons/Setting.svg)。

| 设置 | 描述 |
|--- |--- |
| **[!UICONTROL 地图类型]** | |
| **[!UICONTROL 气泡] | 使用气泡描绘事件。气泡图是一种多变量图表，其形式介于散点图和比例面积图之间。这个视图是默认的。 |
| [!UICONTROL 热图] | 使用热图描绘事件。热图是对数据的图形化呈现，其中以不同颜色表示矩阵中包含的单独值。 |
| **[!UICONTROL 样式]** | |
| [!UICONTROL 颜色主题] | 显示热图和气泡的颜色方案。您可以选择珊瑚色、红色、绿色或蓝色。默认为珊瑚色。 |
| [!UICONTROL 地图样式] | 您可以从基本、街道、明亮、浅色、深色和卫星中选择。 |
| **[!UICONTROL 群集半径]** | 将像素数量在指定范围之内的数据点组合在一起。默认值为 50。 |
| **[!UICONTROL 自定义最大值]** | 允许您更改地图最大值的阈值 — 调整该值即会调整气泡/热图值（颜色和大小）相对于自定义最大值设置的缩放比例。 |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/35170/?quality=12&captions=chi_hans)

-->

