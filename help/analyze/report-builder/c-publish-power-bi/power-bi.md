---
description: 'null'
title: 发布到 Power BI - 概述
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 发布到 Power BI - 概述

Microsoft Power BI是一套用于分析数据和共享洞察的业务分析仪表板。 Adobe Analytics与Power BI的集成使您能在Microsoft Power BI中可视化Report Builder Analytics数据，并在整个组织内轻松共享它。

以前，您作为分析师将计划Report Builder工作簿，以便通过电子邮件（或ftp）分发。 您现在可以在一个基于Web的环境中为业务用户利益相关方提供访问权限（从他们的Power BI帐户中），访问准确、最新的数据，该环境可跨平台和设备访问。

将Report Builder的报表生成功能与Power BI的可视化功能相结合，使组织中的每个人都能更方便地访问信息。 借助Power BI，您还可以将Adobe Analytics与其他数据源（例如销售点、CRM）集成，以发掘独特的客户洞察、关联和机会。

![](assets/aaplusbi.png)

与Adobe Report Builder集成，让您

* [将计划的 Report Builder 工作簿发布到 Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [作为 Power BI 数据集表发布工作簿中所有带格式的表。](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [作为 Power BI 数据集表发布所有 Report Builder 请求](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)

## 系统要求 {#section_0B71092D853446F38FA36447DAC0D32B}

* [已安装](/help/analyze/report-builder/setup/t-install-arb.md) Adobe Report Builder 5.5
* 有效的 Microsoft 帐户允许您登录到 Power BI

## 将工作簿发布到 Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

计划工作簿是带格式的 Excel 电子表格，其中填充了来自 Adobe Analytics 的数据并且会按计划定期发送。

**发布 Report Builder 中的工作簿**

1. 在Report Builder中，生成并保存工作簿。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. 在“基本计划向导”中，选中旁边的复选框 **[!UICONTROL Publish Workbook to Microsoft Power BI]**。

   ![](assets/simple-schedule-wizard.png)

1. 指定电子邮件并立即发送或指定日程安排频率（每小时、每天等）。
1. 单击 **[!UICONTROL OK]** 以发布。
1. 现在将要求您登录您的Microsoft帐户。 提供您的凭据。
1. Report Builder工作簿将被计划并发布到Power BI。

   对于每个计划实例，在Report Builder计划过程用更新的Analytics数据刷新工作簿后，工作簿将发布到Microsoft Power BI。

**在 Power BI 中查看 Report Builder 工作簿数据**

1. 在Power BI中，多次单击菜单下的工 [!UICONTROL Workbooks] 作簿。

   ![](assets/workbooks-power-bi.png)

1. 您现在可以视图工作簿仪表板数据。  ![](assets/view-data-pbi.png)

1. 您随后可以固定此工作簿的一个区域，以便将其包含在您的任意 Power BI 功能板中。

## 作为 Power BI 数据集表，发布工作簿中所有带格式的表 {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE] 如果工作簿包含宏，将禁用“作为 Power BI 数据集表发布工作簿中所有带格式的表”。

除了导入整个工作簿，您只能导入工作簿中所有已设置格式的表的内容。

**用例**:您有一个Excel工作簿，它从多个Report Builder请求中提取数据，并创建一个包含大量公式的摘要表。 您只能将摘要表导入Power BI中并为其创建可视化。

**发布 Report Builder 中带格式的表**

1. 在 Report Builder 中，生成一个数据表，其中包含一个标题行，后面接有一个数据行。
1. 选择表，然后从菜 **[!UICONTROL Format as Table]** 单中进行 [!UICONTROL Home] 选择。 The table gets named by default (Table 1, Table 2, etc.), but you can change the name on the [!UICONTROL Design]menu.

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. 在“基本计划向导”中，单击 **[!UICONTROL Advanced Scheduling Options]**。
1. 在选 [!UICONTROL Scheduling Wizard - Advanced]项卡中，选 **[!UICONTROL Publishing Options]** 中旁边的复选框 **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**。

   ![](assets/advanced-schedule-wizard2.png)

1. （可选）您可以在Power BI中自定义已发布资产的名称。 如果您将版本控制用作工作簿名称的一部分（例如myworkbook_v1.1.xlsx），并且您不希望版本号显示在已发布的Power BI资产的名称中，则此选项非常有用。 它增加了一个优势，即如果版本号发生更改，则发布的资产不会更改。 (此处 [是视图](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) 规范。)

**在 Power BI 中查看表数据**

1. 在Power BI中，转到 **[!UICONTROL Workspaces]** >菜 **[!UICONTROL Datasets]** 单。

   ![](assets/datasets-menu.png)

1. 选择您发布的数据集，然后单击 [!UICONTROL Create report] 其旁边的图标。 请注意，这些表将显示为字段。

   ![](assets/formatted-tables.png)

1. 选择表及其关联的列。

   ![](assets/view-table-dataset.png)

1. 从菜 [!UICONTROL Visualizations] 单中，您可以选择如何在Power BI中可视化表。 例如，您可以选择以线图形式显示数据：

   ![](assets/bi-line-graph.png)

1. 在此处，您可以从此数据集表创建可视化。

## 作为 Power BI 数据集表发布所有 Report Builder 请求 {#section_0C26057C7DBB4068A643FDD688F6E463}

您可以将所有的请求转变为数据集表并在其上构建可视化。

>[!IMPORTANT]
>
>如果工作簿包含 100 个以上的请求，则只有前 100 个请求将被发布到 Power BI。此外，对于发布到Power BI的每个请求，只会发布前10,000行数据。 因此，尽管这些请求将通过计划成功交付，但发布到Power BI的范围有限。

1. 在Report Builder中，打开或创建包含Report Builder请求的工作簿。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. 在“基本计划向导”中，单击 **[!UICONTROL Advanced Scheduling Options]**。
1. 在选 [!UICONTROL Scheduling Wizard - Advanced]项卡中， **[!UICONTROL Publishing Options]****[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]** 选中 ![](assets/advanced-schedule-wizard2.png)

1. 单击 **[!UICONTROL OK]**.

**在 Power BI 中查看请求数据**

每个计划的Report Builder请求将作为数据集中的表发布。 每个请求表都以请求中的主维命名，并且它有一个 [!UICONTROL Report Suite] 和一 [!UICONTROL Segments] 列。

1. 在Power BI中，转到 **[!UICONTROL Workspaces]** >菜 **[!UICONTROL Datasets]** 单。

1. 选择您发布的请求，然后单击 [!UICONTROL Create report] 该请求旁的图标。

   请注意，这些请求在菜单中显示为 [!UICONTROL Fields] 表。

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >无论您如何配置 Report Builder 请求在工作表中的布局（引导布局、自定义布局、某些列不可见），Report Builder 将始终以下列二维单标题行格式发布您的请求：日期、维度、量度、报表包、区段。

1. 另请注意，还有一个名为的附加表 **[!UICONTROL Legend]**。 如果从Report Builder上下文中删除请求，可能很难记住每个请求的含义。 例如，图例表用于在表ID下显示每个请求的名称。 您还可以添加其他“图例”列，以获得请求的完全视图。

   ![](assets/legend-table.png)

