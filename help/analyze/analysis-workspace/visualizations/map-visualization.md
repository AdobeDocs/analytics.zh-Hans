---
description: 在工作区项目中使用地图可视化。
title: 地图
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: e0d14f6dd7be438f3dad979abcfc279e710873e7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 60%

---

# 地图 {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="地图"
>abstract="这种可视化通过在地图中叠加量度来表示。此可视化图表有助于识别不同地理区域的数据。"

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

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的地图可视化图表。_<br/>_在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中当前没有可用的地图可视化。_

>[!ENDSHADEBOX]



Analysis Workspace中的![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL 地图]**&#x200B;可视化图表

* 允许您构建任何量度（包括计算量度）的可视地图，
* 用于识别和比较不同地理区域量度数据，
* 可以支持2个数据源：移动应用的经纬度，或Web应用的地理维度，
* 支持PDF导出，以及
* 利用WebGL进行图形显示。 如果您的图形驱动程序不支持 WebGL 渲染，则可能需要更新您的驱动程序。


>[!BEGINSHADEBOX]

观看演示视频，请参阅Analysis Workspace中的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[地图可视化图表](https://video.tv.adobe.com/v/23559/?quality=12){target="_blank"}。

>[!ENDSHADEBOX]


## 使用

1. 添加![地图](/help/assets/icons/Globe.svg) [!UICONTROL 地图]可视化图表。 请参阅[将可视化图表添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。 您只能将地图可视化拖动到自由格式表的顶部。

   ![映射配置](assets/map-configuration.png){width="50%"}

1. 从下拉列表中选择一个量度。 或从量度列表中拖入量度（包括计算量度）。
1. 指定要从中提取的数据源。 仅当您为移动设备应用程序数据启用了位置跟踪时，才会显示此对话框。

   | 来源 | 描述 |
   | --- | --- |
   | **[!UICONTROL 移动设备经纬度]** | 此选项表示移动应用程序数据。 只有在通过 [!UICONTROL Analytics] > [!UICONTROL 管理员] > [!UICONTROL 报表包] >（选择报表包）> [!UICONTROL 编辑设置] > [!UICONTROL 移动设备管理] > [!UICONTROL 启用位置跟踪]为报表包启用该设置时，才会看到此选项。 默认设置（如果已启用位置跟踪）。 |
   | **[!UICONTROL 地理维度]** | 此选项表示有关访客位置（基于访客的 IP 地址）的按地理位置分段的数据。 此数据将被转换为[!UICONTROL 国家]、[!UICONTROL 地区]和[!UICONTROL 城市]。 请注意，它不会转到 DMA 或邮政编码级别。 几乎所有报表包都启用了此维度。如果您的报表包还没有启用此维度，请联系 Adobe 客户关怀以启用地理报表。 |

1. 选择&#x200B;**[!UICONTROL 生成]**。

   生成了包含气泡的世界地图可视化图表。

   ![](assets/bubble-world-view.png)

1. 您现在可以：

   * 通过双击地图或使用滚轮，**放大**&#x200B;此地图以放大特定区域。地图根据光标的放置位置进行相应的缩放。通过缩放交互，所需的维度（国家/地区 > 州 > 城市）将会根据缩放级别自动更新。
   * 通过并排放置地图可视化，**比较**&#x200B;同一项目中的两个或更多地图可视化。
   * **显示同期（例如，年度）比较信息**：

      * 显示负数：例如，如果您绘制的是年度同比指标，地图会在纽约上方显示 -33%。
      * 对于类型为&#x200B;*百分比*&#x200B;的量度，群集会计算所有百分比的平均值。
      * 绿/红颜色方案：正/负

   * 通过按住 [!UICONTROL Ctrl] 键并移动地图，**旋转** 2D 或 3D 地图。

   * 使用以下描述的[设置](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E)，**切换**&#x200B;到其他视图，如热图。请注意，气泡视图是默认设置。

1. **保存**&#x200B;该项目，以保存所有地图设置（坐标、缩放、旋转）。
1. 通过从左边栏拖入位置维度和量度，填充可视化下方的自由格式表。



## 配置

要重新配置地图可视化图表，请选择![编辑](/help/assets/icons/Edit.svg)。


## 设置

要定义可视化图表的设置，请选择![设置](/help/assets/icons/Setting.svg)。

| 设置 | 描述 |
|--- |--- |
| **[!UICONTROL 映射类型]** | |
| [!UICONTROL 气泡] | 使用气泡描绘事件。气泡图是一种多变量图表，其形式介于散点图和比例面积图之间。此视图是默认视图。 |
| 热图 | 使用热图描绘事件。热图是对数据的图形化呈现，其中以不同颜色表示矩阵中包含的单独值。 |
| **[!UICONTROL 样式]** | |
| [!UICONTROL 颜色主题] | 显示热图和气泡的颜色方案。您可以选择珊瑚色、红色、绿色或蓝色。默认为Coral。 |
| [!UICONTROL 映射样式] | 您可以从基本、街道、明亮、亮、暗和卫星中选择。 |
| **[!UICONTROL 群集半径]** | 将像素数量在指定范围之内的数据点组合在一起。默认值为 50。 |
| **[!UICONTROL 自定义最大值]** | 允许您更改地图最大值的阈值 — 调整该值即会调整气泡/热图值（颜色和大小）相对于自定义最大值设置的缩放比例。 |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)

-->

