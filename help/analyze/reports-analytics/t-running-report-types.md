---
description: 运行不同的报表类型的步骤。
title: 运行不同的报表类型
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: 2bb3cc1ce46fc8e5f7e15291401fce1c4d8cb839
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 94%

---

# 运行不同的报表类型

{{ra-eol}}

您可以在Analysis Workspace中运行多种不同类型的报表。 以下是几个示例。

有关可用的预建报表类型的完整列表，请参阅 [使用预建报表](/help/analyze/analysis-workspace/reports/use-reports.md)

<!-- How do you do a Ranked Report in Workspace?

## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In a ranked report, the table shows the rankings of the report pages in relation to the metric, according to number or percentage. Ranked reports can display multiple metrics in a report.

1. Generate a report, such as a [!UICONTROL Pages Report] ( [!UICONTROL **Workspace**] > **[!UICONTROL Engagement]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. To rank the report, click a column heading in the table.

   Ranked reports can have up to 200 items listed in the table (such as products, categories, web pages, and so on) and ten metrics (revenue, orders, views, and so on).

-->

<!-- Can you do a Trended report? 

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trended reports display metrics over time. You use this report type when you want to see how a segment performs from one time period to the next.

Most Conversion and Traffic reports have a Trended view available. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. Trended reports show trends for a single metric (revenue, orders, views, and so on) for up to five items (such as products, categories, web pages, and so on).

**To run a trended report** 

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

-->

## 运行流失报表 {#task_8FD97C8260464F9DA731A93DB8F80184}

[!UICONTROL 流失报表]显示访问预先指定的页面顺序的访客数。它还显示每个步骤之间的转化和流失百分比。

在 Analysis Workspace 中查看新的[流失分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)面板！

1. 在 [!UICONTROL Adobe Analytics] 中，单击&#x200B;**[!UICONTROL 报表]** > **[!UICONTROL 路径]** > **[!UICONTROL 页面]** > **[!UICONTROL 流失]**。
1.  在[!UICONTROL 流失报表]页面上，单击&#x200B;**[!UICONTROL 启动流失 Report Builder]**。

1.  在[!UICONTROL 定义检查点]页面上，指定要用于报表的检查点。
1. 单击&#x200B;**[!UICONTROL 运行报告]**。

## 运行页面流量报表 {#task_133E8B87C3F04DA0A42D10CBA499305B}

页面流量报表显示访客访问页面和导航网站的顺序。此报表有助于解答相关问题。

例如，单击 **[!UICONTROL 工作区]** > **[!UICONTROL 报表]** > **[!UICONTROL 参与]** > **[!UICONTROL 下一页和上一页流量]**.

## 运行营销渠道报表 {#task_64ADED5CC75248319E06E3E029B47F78}

营销渠道报表提供第一个和最后一个渠道分配的概要报表，并显示标准的报表量度，如收入、订购和成本等。使用这些报表可以分析每个渠道产生的收入量。

有关更多信息，请参阅[营销渠道](/help/components/c-marketing-channels/analyze-mc.md)帮助系统。

## 运行异常检测报表 {#task_4808C96327354D789C075823F5C3A049}

您可以运行 [异常检测和贡献分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=zh-Hans) 仅在Analysis Workspace中。

## 运行实时报表 {#task_5D25929C918E40B18965222FA94176B0}

描述如何查看和解读实时报表。

**[!UICONTROL 报表 > 网站量度 > 实时]**。

实时报表提供了两个主要的报表 - 概述报表和详细信息报表。每个报表都包含许多缩图报表。

请参阅 [实时报表概述](/help/components/c-real-time-reporting/realtime.md) 以了解更多信息。

1. 了解&#x200B;**[!UICONTROL 概述]**&#x200B;报表及其组件：![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> 用户界面组件 </th> 
   <th class="chdeschd"> 描述 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>选择报表包</strong></td> 
   <td class="chdesc stentry"> 显示此实时报表涵盖的报表包。要更改报表包，请参阅<a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html"  >实时报表配置</a>。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>切换报表</strong></td> 
   <td class="chdesc stentry"> 您可以在设置的报表（最多 3 个）间切换。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>选择时间范围</strong></td> 
   <td class="chdesc stentry"> 您可以选择报表中的所有缩图报表使用的整体时间范围。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>配置报表</strong></td> 
   <td class="chdesc stentry"> 仅当您具备管理员权限时，才能看到这个齿轮图标链接。单击该链接可访问位于<span class="ignoretag"><span class="uicontrol">管理工具</span> &gt; <span class="uicontrol">报表包</span> &gt; <span class="uicontrol">编辑设置</span> &gt; <span class="uicontrol">实时</span></span>中的报表包管理器。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>全屏视图</strong></td> 
   <td class="chdesc stentry"> 仅当您的显示器具有特定的纵横比（16:9 或 16:10）并且浏览器对此提供支持时，才能看到全屏视图图标。请注意，当屏幕处于全屏模式时，您无法与屏幕进行交互（按 <span class="uicontrol">Esc</span> 可退出）。全屏模式不涉及超时。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>网站流量缩图报表</strong></td> 
   <td class="chdesc stentry"> 蓝色的趋势线数据显示了整个网站的总流量。除了作为实时表达而显示的当前值之外，X 轴还使用文字标签（15 分钟前、10 分钟前）。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>网站总计缩图报表</strong></td> 
   <td class="chdesc stentry"> 显示实时报表的选定量度在最近 N 分钟内的网站总计计数。可以通过时间范围选择器对“N”进行配置。 <p>箭头颜色和方向基于以下算法： 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">显著获胜（向上箭头）：大于 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">获胜（右上箭头）：5% 至 100% </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> 平稳（向右箭头）：5% 至 -5% </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> 失败（右下箭头）：-5% 至 -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> 显著失败（向下箭头）：小于 -100% </li> 
      </ul> </p> <p>如果网站总计以“实例数”进行报告，则这些实例数反映主要缩图报表中的维度。如果存在特定于实例的名称（例如“页面查看”），则网站总计会报告该名称。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>主要缩图报表</strong></td> 
   <td class="chdesc stentry"> 有关实时报表的主要维度及其量度的报表。显示该元素在选定时间范围内的趋势线。量度总计显示完整趋势线的总和。箭头指示该项目是显著获胜、获胜、平稳、失败还是显著失败。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>搜索对话框</strong></td> 
   <td class="chdesc stentry"> 搜索会对所有缩图报表产生影响。在您查看报表时，搜索会持续进行。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>按最受欢迎/获胜方/失败方进行排序</strong></td> 
   <td class="chdesc stentry"> 您可以按<span class="uicontrol">最受欢迎</span>（默认）、<span class="uicontrol">获胜方</span>（显示增长最多的维度）和<span class="uicontrol">失败方</span>（处于下跌轨迹的维度）切换排序。 <p>下面是用来确定获胜方或失败方的公式：“实时”查看最早的示例和接近最新的示例，然后执行简单的“% 变更”计算。如果选定“最近 15 分钟”，且 n 代表当前时间，则会计算 n-1 与 n-15 期间的变更情况。“实时”当前不执行任何加权操作。当前的时间（分钟）会被忽略，因为它没有完成，而且可能会产生一个错误的 % 变更。 </p> <p>这个公式对于实时报表中用到的所有量度来说，都是一致的。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 1 缩图报表</strong></td> 
   <td class="chdesc stentry"> 显示第二次配置的报表的维度和量度的实时报表。 <p>次要 1 缩图报表显示了前 4 个类别；第 5 个类别是关于所有剩余值的聚合。对于每个类别，缩图报表均提供了该类别的原始查看总数。此外，所有类别的总计情况显示在中心位置。 </p> <p> 将鼠标悬停在某个区域上可突出显示相关的类别，并会在同心圆下方显示该类别的趋势线。 </p> <p> 将鼠标悬停在某个行项目上可突出显示该行项目及其相关的区域，并会在同心圆下方显示该类别的趋势线。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 2 缩图报表</strong></td> 
   <td class="chdesc stentry"> 显示第三次配置的报表的维度和量度的实时报表。将鼠标悬停在项目标签上可向右滑动标签，并为该悬停项目显示一条趋势线。 </td> 
   </tr> 
   </table>

2. 单击主要缩图报表中的列表项，以便为该列表项启动&#x200B;**[!UICONTROL 详细信息]**&#x200B;视图：![](assets/rtr_detail_report.png)

   | **项目趋势缩图报表** | 显示概述报表中选定的项目在最近 N 分钟内的趋势线。可以通过时间范围选择器对 N 进行配置。 |
   |---|---|
   | **项目总计缩图报表** | 显示概述报表中选定的项目在最近 N 分钟内的量度总计数。可以通过时间范围选择器对 N 进行配置。 |
   | **关联的次要 1 缩图报表** | 此缩图报表与次要 1 缩图报表非常相似。二者唯一的区别在于用来填充此报表的数据源：在本示例中，它显示了特定页面（在概述报表的主要缩图报表中选定的页面）与查看的实例之间的关联（或划分）。 |
   | **关联的次要 2 缩图报表** | 此缩图报表与次要 2 缩图报表非常相似。二者唯一的区别在于用来填充此报表的数据源：在本示例中，它显示了特定页面（在概述报表的主要缩图报表中选定的页面）与语言维度之间的关联（或划分）。 |
