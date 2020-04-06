---
description: 运行报告后，您可以自定义报告以根据您的需求视图和分析数据。 您可以过滤报告数据、更改以图形方式呈现数据的方式、更改日期粒度等。
title: 自定义报表概述
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 自定义报表概述

运行报告后，您可以自定义报告以根据您的需求视图和分析数据。 您可以过滤报告数据、更改以图形方式呈现数据的方式、更改日期粒度等。

## 创建自定义报表 {#task_BA6EACA3039C40AEA5605E1D8C76E646}

描述如何将报表的当前配置另存为可供所有用户查看的新自定义报表的步骤。

<!-- 

t_reports_custom.xml

 -->

只有管理员才能创建自定义报告。 创建自定义报告时，它将添加到其所基于的报告旁的主报告菜单。

**创建自定义报告**

1.  运行报表并根据需要进行配置。
1. 单击 **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   确保与现有报表名不重复。

>[!MORELIKETHIS]
>
>* [菜单自定义](https://marketing.adobe.com/resources/help/zh_CN/reference/customize_menus.html)


## 选择日期或日期范围 {#task_9BEF7D4D839A4748B76E8500D1406C34}

描述常用的步骤，为报表数据选择时间段。

<!-- 

t_reports_select_date.xml

 -->

您可以选择特定的天、周、月或年。 您还可以运行比较报告。

当您打开包含具有不同日期范围的缩图报表的仪表板时，您可以在日历中选择新的日期范围。 这些更改适用于仪表板中的所有缩图报表。

**选择日期范围**

1. 运行报表。
1. 单击右上方的日历图标。
1. 选择日期。

   您可以:

   * 视图天数、月数或年度期间（最多三个）。
   * 跨日期拖动光标以选择范围。
   * 手动输入日期。
   * 单击月份名称以选择月份。
   * 单击 **[!UICONTROL Select Preset]** 以选择预设日期。
   * 比较日期.

1. 单击 **[!UICONTROL Run Report]**.

## 比较日期 {#task_95155C3700774B709F5FB81AE96B0824}

描述如何使用日历在排名报表之间运行日期比较的步骤。

<!-- 

t_reports_comparing_dates.xml

 -->

您无法比较趋势报表之间的日期。

>[!NOTE] 如果您想对功能板中的关键量度执行日期比较，则可以使用两个不同的请求，将数据提取到 [Report Builder](https://marketing.adobe.com/resources/help/zh_CN/arb/) 中。然后，可以在 Excel 中使用自定义公式来分析二者的差异。

要比较“报告与分析”中排名报表之间的日期，请执行以下操作：

1. 运行报表。
1. 单击右上方的日历。
1. 单击 **[!UICONTROL Compare Dates]**.
1.  选择要使用的日期。
1. 单击 **[!UICONTROL Run Report]**.

## 将百分比显示为图表 {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

描述如何指定是否以图形形式在报表表格中显示百分比的步骤。

<!-- 

t_reports_graph_percent.xml

 -->

此可视化功能也可在仪表板报告中使用。

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. 单击 **[!UICONTROL Percent Shown As: Graph]**.

## 标准化报表数据 {#task_8005B55E59BD479DA67BC618FF8BC94A}

描述如何标准化报表数据的步骤。

<!-- 

t_reports_normalize.xml

 -->

在运行具有比较日期的报表或A/B比较后，您可以将数据标准化以显示报表之间的更改百分比。 调整辅助数据集以补偿所选天数或不同流量的差异。

**标准化报表数据**

1.  运行支持数据比较的报表
1. 单 **[!UICONTROL Compare Dates]**&#x200B;击，然后指定日期比较。
1. 单击 **[!UICONTROL Run Report]**.
1. 单击 **[!UICONTROL Normalize Data: Yes]**.

## 为报表选择页面 {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

描述如何从网站页面中为报表选择特定页面的步骤。

<!-- 

t_reports_select_page.xml

 -->

1. 生成报表，如 [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**)。
1. Click the **[!UICONTROL Selected Page]** link.
1. On [!UICONTROL Choose Page], select the pages you want to display.
1.  查找页面。
1. 单击 **[!UICONTROL OK.]**

## 比较报表包 {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

描述如何在同一报表中显示两个报表包中的报表的步骤。

<!-- 

t_reports_compare_suites.xml

 -->

除了图形显示，报表的表格还为您提供百分比比较。 可以比较运行以下报告：

* 网站内容
* 移动设备
* 流量源
* 促销活动
* 产品
* 访客维系
* 访客资料
* 自定义转化
* 自定义流量
* Target
* 调查

**比较报表包**

1.  生成可以比较报表的报表。
1. Click the **[!UICONTROL Compare to Site]** link.
1.  查找报表包。
1. 单击 **[!UICONTROL OK.]**

## 指定报表粒度 {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

描述如何按小时、每日、每周、每月、每季度或每年视图报告总计的步骤。

<!-- 

t_reports_granularity.xml

 -->

报告的时间段决定了可用的粒度选项。 例如，只有选择了一 **[!UICONTROL Hourly]** 天或两天的时间范围，才能进行选择。 只有选择了 **[!UICONTROL Yearly]** 超过一年的粒度时，才能选择粒度。

**指定报告粒度**

1. 生成趋势报表，如 **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## 运行星期报表 {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

描述如何在一周中的特定日期（如给定日期范围内的每个星期一）运行报告的步骤。

<!-- 

t_reports_day_of_week.xml

 -->

此功能仅适用于按“周”或“日”日期范围筛选的趋势报表。

1.  在指定日期范围内运行趋势报表。
1. 单击链 **[!UICONTROL Day of Week]** 接，然后单击某天。

## “在工作区尝试”按钮{#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

单击 **[!UICONTROL Try In Workspace]** 报表顶部的按钮将在分析工作区中加载同一报表。

<!-- 

try_in_workspace.xml

 -->

Reports &amp; Analytics中的大多数报告现在都包含“在工作区中试用”按钮，允许您在分析工作区中重现当前视图，以便进一步自定义。

当前，仅当您的用户名对分析工作区具有完全权限时，此按钮才可用。

有关自定义报告的所有方式的详细信息，请参阅 [分析工作区指南](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/) 。
