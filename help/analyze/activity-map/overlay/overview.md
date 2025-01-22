---
description: 了解Activity Map扩展以及如何导航其界面。
title: Activity Map扩展界面
uuid: f6734b60-0b77-4f50-a45a-6a6936d1524e
feature: Activity Map
role: User, Admin
exl-id: 461abda1-3238-4a32-b9d3-5a57b00cf0d3
source-git-commit: 13ad9d40ad74a8dffe05d899db54f4d77cbcc34c
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---

# Activity Map扩展界面

Activity Map扩展界面由两部分组成：

* 一个顶部面板，可让您配置扩展和报表
* 显示最受欢迎链接的叠加图
* 显示最受欢迎链接量度的底部面板

## 顶部面板

顶部面板包含用于Activity Map叠加的基本控件。

![叠加](../assets/overlay.png)

它提供以下设置：

* **标准/实时视图**：在标准视图和实时视图之间切换。
   * 标准视图：显示基于历史数据的叠加。
   * 实时视图：显示基于实时数据的叠加图。 日期选择器将更改为下拉列表，允许您更改实时数据的粒度。
* **量度选择器**：允许您更改叠加报表的量度。 如果您选择了实时视图，则只有[!UICONTROL 链接点击次数]可用。
* **区段选择器**：允许您选择一个[区段](/help/components/segmentation/seg-overview.md)，并查看叠加图中的数据子集。 区段在实时视图中不可用。
* **叠加可视化类型**：允许您更改叠加可视化链接排名的方式。
   * **[!UICONTROL 气泡]**：热门链接收到一个绿色气泡，显示其在报告期间的数值排名。 您可以在[设置](settings.md)中更改气泡颜色。
   * **[!UICONTROL 渐变]**：排名最前的链接显示为透明红色。 最受欢迎的链接是最暗的红色。 您可以在[设置](settings.md)中更改渐变颜色。
   * **[!UICONTROL 关闭]**：禁用链接叠加。
* **日期选择器**：允许您更改报告周期。

此面板的标题包含以下设置：

* **展开/折叠顶部面板**：切换顶部面板以水平或垂直显示设置（双箭头图标）。
* **[!UICONTROL 切换页面详细信息]**：显示或隐藏底部面板（眼睛图标）。
* **[!UICONTROL 显示设置]**：打开一个菜单，以显示可更改的设置（齿轮图标）：
   * **[!UICONTROL 设置]**：打开扩展的[设置](settings.md)。
   * **[!UICONTROL 帮助]**：打开文档以Experience League（此页面）。
   * **[!UICONTROL Adobe社区]**：打开[Experience League社区](https://experienceleaguecommunities.adobe.com/)。
   * **[!UICONTROL 关于]**：显示扩展版本。
   * **[!UICONTROL 注销]**：将您从扩展注销，要求您重新登录。
* **[!UICONTROL 退出Activity Map]**：关闭扩展的所有叠加图（X图标）。

## 页面叠加

页面叠加图包含您的网站内容，以及一个显示报告期内点击的最受欢迎链接位置的叠加。 您可以将这些链接叠加配置为在顶部面板的&#x200B;**[!UICONTROL 叠加可视化类型]**&#x200B;中显示为气泡或渐变。

如果单击气泡或渐变，则可以查看该特定链接的详细信息。

![链接气泡](../assets/link-bubble.png)

## 底部面板

底部面板显示在叠加图上显示的链接的汇总视图。

* **报表类型**：切换底部面板以显示&#x200B;]**页面上的**[!UICONTROL &#x200B;链接报表或&#x200B;**[!UICONTROL 页面详细信息]**&#x200B;报表。
* **[!UICONTROL 页面名称]**：当前[页面](/help/components/dimensions/page.md)维度名称。
* **[!UICONTROL 搜索]**：筛选报告以仅显示与输入文本匹配的链接名称。
* **[!UICONTROL 下载]**：将报表导出为CSV。 您可以将页面]上的[!UICONTROL 链接报表、[!UICONTROL 页面]报表和[!UICONTROL 页面流量]报表包含在同一个下载文件中。
* **[!UICONTROL 更改报表停靠位置]**：切换此面板的位置，使其显示在浏览器窗口的底部或顶部。
* **[!UICONTROL 关闭报告]**：关闭此面板。 您可以使用顶部面板中的&#x200B;**[!UICONTROL 切换页面详细信息]**&#x200B;按钮（眼睛图标）再次打开该面板。

**[!UICONTROL 页面]**&#x200B;上的链接报表显示的基本工作区报表具有以下设置：

* [Activity Map链接](/help/components/dimensions/activity-map-link.md)维度
* [发生次数](/help/components/metrics/occurrences.md)量度（标记为&#x200B;**[!UICONTROL 链接点击次数]**）
* 当前[Page](/help/components/dimensions/page.md)值已应用为区段

页面面板上的![链接](../assets/links-on-page.png)

**[!UICONTROL 页面详细信息]**&#x200B;报表显示使用[页面](/help/components/dimensions/page.md)维度的[流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)可视化图表，重点是当前页面。 当前页面的以下量度显示在左侧：

* 总共[次页面查看](/help/components/metrics/page-views.md)
* 所有页面查看次数的[!UICONTROL %]
* [条目](/help/components/metrics/entries.md)计数
* [退出](/help/components/metrics/exits.md)计数
* [单页面访问量](/help/components/metrics/single-page-visits.md)
* [!UICONTROL 页面平均点击次数]
* [页面平均逗留时间](/help/components/metrics/time-spent.md)
* [重新加载的次数](/help/components/metrics/reloads.md)
* [跳出率](/help/components/metrics/bounce-rate.md)
* [!UICONTROL 链接点击次数]

![详细信息页面](../assets/page-details.png)
