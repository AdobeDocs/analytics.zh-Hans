---
description: 运行报表后，您可以自定义报表，以根据需要查看和分析数据。您可以过滤报表数据，以图形方式更改数据的呈现方式，更改日期粒度等。
title: 自定义报表概述
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: ad9a7729924636055e456d0fd7ab928be227034d

---


# 自定义报表概述

运行报表后，您可以自定义报表，以根据需要查看和分析数据。您可以过滤报表数据，以图形方式更改数据的呈现方式，更改日期粒度等。

## 创建自定义报表 {#task_BA6EACA3039C40AEA5605E1D8C76E646}

描述如何将报表的当前配置另存为新的自定义报表以供所有用户查看的步骤。

<!-- 

t_reports_custom.xml

 -->

只有管理员可以创建自定义报表。在创建自定义报表后，会将其添加到所依据的报表旁边的主报告菜单中。

**创建自定义报表**

1.  运行报表并根据需要进行配置。
1. 单击 **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   确保与现有报表名不重复。

>[!MORELIKETHIS]
>
>* [菜单自定义](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/customize-menus.html)


## 选择日期或日期范围 {#task_9BEF7D4D839A4748B76E8500D1406C34}

描述如何为您的报表数据选择时段的步骤。

<!-- 

t_reports_select_date.xml

 -->

可选择特定的日、星期、月或年。还可以运行比较报表。

打开包含缩图报表（有不同日期范围）的功能板时，您可以在日历中选择新的日期范围，所做的更改会应用到功能板中的所有缩图报表。

**选择日期范围**

1. 运行报表。
1. 单击右上方的日历图标。
1. 选择日期。

   您可以:

   * 查看日、月或年时间段（多达三个）。
   * 在日期中拖动光标选择一个范围。
   * 手动输入日期。
   * 单击某个月名选择月份。
   * 单击 **[!UICONTROL Select Preset]** 以选择预设日期。
   * 比较日期.

1. 单击 **[!UICONTROL Run Report]**.

## 比较日期 {#task_95155C3700774B709F5FB81AE96B0824}

描述如何使用日历在排名报表之间运行日期比较的步骤。

<!-- 

t_reports_comparing_dates.xml

 -->

您无法在趋势报表之间比较日期。

>[!NOTE] 如果您想对功能板中的关键量度执行日期比较，则可以使用两个不同的请求，将数据提取到 [Report Builder](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/report-builder/home.html) 中。然后，可以在 Excel 中使用自定义公式来分析二者的差异。

要比较“Reports &amp; Analytics”中排名报表之间的日期，请执行以下操作：

1. 运行报表。
1. 单击右上方的日历。
1. 单击 **[!UICONTROL Compare Dates]**.
1.  选择要使用的日期。
1. 单击 **[!UICONTROL Run Report]**.

## 将百分比显示为图表 {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

描述如何指定是否在报表表格中将百分比显示为图表的步骤。

<!-- 

t_reports_graph_percent.xml

 -->

该可视化功能也可用于功能板缩图报表。

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. 单击 **[!UICONTROL Percent Shown As: Graph]**.

## 标准化报表数据 {#task_8005B55E59BD479DA67BC618FF8BC94A}

描述如何标准化报表数据的步骤。

<!-- 

t_reports_normalize.xml

 -->

运行含比较日期，或用于 A/B 比较的报表后，您可将数据标准化，以显示报表的更改百分比。将调整次级数据集以补偿所选日差数或流量差。

**标准化报表数据**

1.  运行支持数据比较的报表
1. 单击 **[!UICONTROL Compare Dates]**，然后指定日期比较。
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

描述如何在同一报表中显示来自两个报表包的报表的步骤。

<!-- 

t_reports_compare_suites.xml

 -->

除图形显示以外，报表的表格部分还可提供百分比比较。以下报表可使用比较功能运行：

* 网站内容
* 移动设备
* 流量源
* 促销活动
* 产品
* 访客维系
* 访客资料
* 自定义转换
* 自定义流量
* Target
* 调查

**比较报表包**

1.  生成可以比较报表的报表。
1. Click the **[!UICONTROL Compare to Site]** link.
1.  查找报表包。
1. 单击 **[!UICONTROL OK.]**

## 指定报表粒度 {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

描述如何按每小时、每天、每周、每月、每季或每年查看报表合计的步骤。

<!-- 

t_reports_granularity.xml

 -->

报表的时段确定哪些粒度选项可用。For example, you can select only **[!UICONTROL Hourly]** if you have a one or two day time frame selected. You can select only **[!UICONTROL Yearly]** granularity if you have more than one year selected.

**指定报表粒度**

1. 生成趋势报表，如 **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## 运行星期报表 {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

描述如何在每周特定的日期运行报表（例如在指定日期范围内的每个星期一）的步骤。

<!-- 

t_reports_day_of_week.xml

 -->

该功能仅适用于通过周或日过滤的“趋势”报表。

1.  在指定日期范围内运行趋势报表。
1. 单击链 **[!UICONTROL Day of Week]** 接，然后单击某天。

## “在工作区尝试”按钮{#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Clicking the **[!UICONTROL Try In Workspace]** button at the top of a report will load the same report in Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

“Reports &amp; Analytics”中的大多数报表现在包括“在工作区尝试”按钮，以便您可以在 Analysis Workspace 中重现当前视图以进一步自定义报表。

目前，仅当您的用户名拥有 Analysis Workspace 的完整访问权限时，该按钮才可用。

有关可以自定义报表的所有方法的更多信息，请参阅 [Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) 指南。
