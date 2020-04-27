---
description: 使用 AND/OR 搜索表达式通过布尔逻辑配置的排名和条件过滤器。
title: 最受欢迎的过滤设置
topic: Report builder
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 最受欢迎的过滤设置

使用 AND/OR 搜索表达式通过布尔逻辑配置的排名和条件过滤器。

大多数常用过滤器是使用Boolean逻辑与AND/OR条件(如与条件或条件组（如、或）)配置的表达式 [!UICONTROL Page does not contain]*`<product name>`*[!UICONTROL Includes All][!UICONTROL Includes Any][!UICONTROL Excludes All]过滤器。 您可以[保存](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md)这些表达式，供此工作簿或其他工作簿中的其他请求使用。

**创建最受欢迎的过滤器**

1. 创建或编辑请求，然后前进到 [!UICONTROL Request Wizard: Step 2]。

   ![步骤信息](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.
1. 在表单 [!UICONTROL Choose Page] 上，启 **[!UICONTROL Most Popular]**&#x200B;用，然后配置以下选项：

   **起始排名：**&#x200B;维度的起始排名。默认排名 1 表示在报告的数据列表中排在第 1 位的项目。For example, for the dimension [!UICONTROL Page], a starting mark of 1 indicates the single most requested page of your site. 您可以指定 10 或另一值作为起始排名单元格，这样会生成将 10 作为最高排名的报表。量度按降序排列，以便系统首先在列表中报告具有最高活动频率的行项目。如果您在一个请求中需要超过 50,000 个页面名称，但是您已要求系统报告数千个页面的数据，则可以复制请求并更改起始排名，以在 50,000 个数据块中检索相应数据。

   **条目数：** (仅 [!UICONTROL Pivot Layout] 限)定义在某个日期范围内报告特定度量的项目数。 一些量度可能会列出上百个条目，而其他量度可能只显示几个条目。For example, for the dimension [!UICONTROL Site Section], a number of entries of 25 indicates that the report shows the 25 most visited pages.

   使用箭头可以更改 [!UICONTROL Starting Rank] 工作表 [!UICONTROL Number of Entries] 中第一个数据点的和。 默认情况 [!UICONTROL Starting Rank] 下，设置为1，设置为 [!UICONTROL Number of Entries] 10。 对于某些量度，这些值可在 1（下限）到 50,000（上限）之间调整。每个指标都有自己的上限 [!UICONTROL Number of Entries]。 不允许在这些字段中使用负值或 0。If you choose a [!UICONTROL Starting Rank] as 15 and [!UICONTROL Number of Entries] as 10, data requests for the metric return the 10 most visited pages, where the first most visited page is number 15 in the list for the specific date range. 系统按降序列出排名介于 15 至 25 之间的所有请求次数最多的页面。

   >[!NOTE]
   >
   >对现有请求应用过滤器会导致提供的数据发生变化。假设您将前10个元 [!UICONTROL Pages] 素映射到单元格$A$1到$A$10，其中1表示， [!UICONTROL Starting Rank] 10表示 [!UICONTROL Number of Entries]。 If you change these values to show 1 for [!UICONTROL Starting Rank] and only 3 for [!UICONTROL Number of Entries], the data previously filling cells $A$4 through $A$10 will no longer appear.

1. To create a search expression, click **[!UICONTROL Add]**.

   ![步骤信息](assets/expressions_define_filter.png)

1. On the [!UICONTROL Define Filter] form, configure the conditions appropriate for your needs.

   ![select_cell_icon.png](assets/select_cell_icon.png)：允许您查找在单元格值中定义的条件。

   **添加条件：**&#x200B;向表达式添加条件。可添加的条件数没有限制。

1. 单击 **[!UICONTROL OK]**.

   ![步骤信息](assets/choose_page_02.png)

1. 在表单 [!UICONTROL Choose Page] 上，单 **[!UICONTROL Save]** 击以保存表达式。
1. 单击 **[!UICONTROL OK]**.
