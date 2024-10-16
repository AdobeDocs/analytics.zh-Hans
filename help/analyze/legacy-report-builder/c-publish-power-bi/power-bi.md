---
description: 将 Report Builder 用于 Microsoft Power BI。
title: 发布到 Power BI — 概述
feature: Report Builder
role: User, Admin
exl-id: 3464c153-2db5-41af-9e83-da081ec64ad3
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 100%

---

# 发布到 Power BI — 概述

Microsoft Power BI 是一组用来分析数据和共享分析的业务分析功能板。Adobe Analytics 与 Power BI 的集成允许您在 Microsoft Power BI 内可视化 Report Builder Analytics 数据，并在组织范围内轻松共享。

作为分析师，您之前使用电子邮件或 ftp 计划 Report Builder 工作簿分发。现在，您可以让您的业务利益相关者在一个基于 Web 的环境（可跨各类平台和设备访问）中，从他们的 Power BI 帐户内访问准确和最新的数据。

通过将 Report Builder 的报表生成功能与 Power BI 的可视化功能相结合，组织中的每个人都可以更加轻松地访问信息。通过 Power BI，您还可以将 Adobe Analytics 与其他数据源（如销售点或 CRM 源）集成以发现独特的客户洞察、关联和机会。

![包含 Microsoft Power BI 图标和 Adobe Analytics 图标的图表。](assets/aaplusbi.png)

## 系统要求 {#section_0B71092D853446F38FA36447DAC0D32B}

* [已安装](/help/analyze/legacy-report-builder/setup/t-install-arb.md) Adobe Report Builder 5.5
* 有效的 Microsoft 帐户允许您登录到 Power BI

## 将工作簿发布到 Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

计划工作簿是带格式的 Excel 电子表格，其中填充了来自 Adobe Analytics 的数据，这些数据会按计划定期分发。

**发布 Report Builder 中的工作簿**

1. 在 Report Builder 中，生成并保存工作簿。
1. 在 Report Builder 工具栏上，单击&#x200B;**[!UICONTROL 计划]** > **[!UICONTROL 新建]**。

1. 在“基本计划向导”中，选中&#x200B;**[!UICONTROL 将工作簿发布到 Microsoft Power BI]** 旁边的复选框。

   ![Report Builder 计划向导的屏幕快照，其中显示选中的“将工作簿发布到 Microsoft Power BI”选项。](assets/simple-schedule-wizard.png)

1. 指定您的电子邮件并立即发送，或指定计划发布频率（每小时、每天等）。
1. 单击&#x200B;**[!UICONTROL 确定]**&#x200B;继续。
1. 系统随即将要求您登录到您的 Microsoft 帐户。提供您的凭据。
1. Report Builder 工作簿将被计划并发布到 Power BI。

   通过每个计划实例，在 Report Builder 计划过程已为工作簿刷新更新的 Analytics 数据之后，该工作簿将被发布到 Microsoft Power BI。

**在 Power BI 中查看 Report Builder 工作簿数据**

1. 在 Power BI 中，双击[!UICONTROL 工作簿]菜单下方的工作簿。

   ![Power BI 工作簿视图的屏幕快照。](assets/workbooks-power-bi.png)

1. 现在您可以查看工作簿仪表板数据。![工作簿仪表板数据。](assets/view-data-pbi.png)

1. 您随后可以固定此工作簿的一个区域，以便将其包含在您的任意 Power BI 仪表板中。

## 作为 Power BI 数据集表，发布工作簿中所有带格式的表 {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>如果工作簿包含宏，将禁用“作为 Power BI 数据集表发布工作簿中所有带格式的表”。

您无需导入整个工作簿，只用导入工作簿内所有带格式的表的内容。

**用例：**&#x200B;您可以让一个 Excel 工作簿提取多个 Report Builder 请求中的数据并通过许多公式创建一个摘要表。您只需将此摘要表导入 Power BI 并为其创建一个可视化图表。

**发布 Report Builder 中带格式的表**

1. 在 Report Builder 中，生成一个数据表，其中包含一个标题行，后面接有一个数据行。
1. 选择此表，然后从[!UICONTROL 主页]菜单中选择&#x200B;**[!UICONTROL 套用表格式]**。此表将得到默认命名（Table 1, Table 2 等），但是您可以在[!UICONTROL 设计]菜单中更改名称。

1. 在 Report Builder 工具栏上，单击&#x200B;**[!UICONTROL 计划]** > **[!UICONTROL 新建]**。

1. 在“基本计划向导”中，单击&#x200B;**[!UICONTROL 高级计划选项]**。
1. 在[!UICONTROL 计划向导 — 高级]内的&#x200B;**[!UICONTROL 发布选项]**&#x200B;选项卡中，选中&#x200B;**[!UICONTROL 作为 Power BI 数据集表发布所有带格式的表]**&#x200B;旁边的复选框。

   ![显示“计划向导 - 高级”内的“发布选项”的屏幕快照，带“作为 Power BI 数据集表发布所有带格式的表”选项。](assets/advanced-schedule-wizard2.png)

1. （可选）您可以在 Power BI 中自定义已发布资产的名称。如果您在工作簿名称中使用版本控制（例如，myworkbook_v1.1.xlsx），但又不希望版本号在已发布的 Power BI 资产名称中显示，这一操作将非常有用。它的优势在于，已发布的资产不会随着版本号的更改而更改。（查看此处的[规范](/help/analyze/legacy-report-builder/c-publish-power-bi/specifications-limits.md)。）

**在 Power BI 中查看表数据**

1. 在 Power BI 中，转到&#x200B;**[!UICONTROL Workspace]** > **[!UICONTROL 数据集]**&#x200B;菜单。

   ![显示突出显示“创建报告”的 Power BI 数据集菜单的屏幕快照。](assets/datasets-menu.png)

1. 选择已发布的数据集，并单击它旁边的[!UICONTROL 创建报表]图标。请注意，表将显示为字段。

   ![显示选定的已发布数据集的屏幕快照，其中将表作为字段列出。](assets/formatted-tables.png)

1. 选择一个表及其关联的列。

   ![显示选定表与关联列的屏幕快照](assets/view-table-dataset.png)

1. 从[!UICONTROL 可视化]菜单中，您可以选择如何可视化 Power BI 中的表。例如，您可以选择以折线图的形式呈现您的数据：

   ![显示“可视化”菜单和数据折线图的屏幕快照。](assets/bi-line-graph.png)

1. 在这里，您可从该数据集表创建可视化。

## 作为 Power BI 数据集表发布所有 Report Builder 请求 {#section_0C26057C7DBB4068A643FDD688F6E463}

您可以将所有的请求转变为数据集表并在其上构建可视化。

>[!IMPORTANT]
>
>如果工作簿包含 100 个以上的请求，则只有前 100 个请求将被发布到 Power BI。此外，对于发布到 Power BI 的每个请求，只有前 10,000 行数据将获得发布。因此，尽管这些请求将通过计划成功地提交，但发布到 Power BI 的范围却是有限的。

1. 在 Report Builder 中，通过 Report Builder 请求打开或创建一个工作簿。
1. 在 Report Builder 工具栏上，单击&#x200B;**[!UICONTROL 计划]** > **[!UICONTROL 新建]**。

1. 在“基本计划向导”中，单击&#x200B;**[!UICONTROL 高级计划选项]**。
1. 在[!UICONTROL 计划向导 - 高级]内的&#x200B;**[!UICONTROL 发布选项]**&#x200B;选项卡上，选中&#x200B;**[!UICONTROL 作为 Power BI 数据集表发布所有 Report Builder 请求]**&#x200B;旁边的框。![显示计划向导的屏幕快照，其中突出显示了“作为 Power BI 数据集表发布所有 Report Builder 请求”选项。](assets/advanced-schedule-wizard2.png)

1. 单击&#x200B;**[!UICONTROL 确定]**。

**在 Power BI 中查看请求数据**

每个计划的 Report Builder 请求都将作为数据集中的表发布。每个请求表均按照请求中的主要维度命名，并具有“[!UICONTROL 报表包]”和“[!UICONTROL 区段]”列。

1. 在 Power BI 中，转到&#x200B;**[!UICONTROL Workspace]** > **[!UICONTROL 数据集]**&#x200B;菜单。

1. 选择已发布的请求并单击它旁边的“[!UICONTROL 创建报表]”图标。

   请注意，请求会显示为“[!UICONTROL 字段]”菜单中的表。

   ![显示以二维单标题行格式发布的选定请求的屏幕快照。](assets/published-requests.png)

   >[!NOTE]
   >
   >无论您如何配置 Report Builder 请求在工作表中的布局（引导布局、自定义布局、某些列不可见），Report Builder 将始终以下列二维单标题行格式发布您的请求：日期、维度、量度、报表包、区段。

1. 另请注意，还有一个称为&#x200B;**[!UICONTROL 图例]**&#x200B;的表。如果有请求不属于 Report Builder 环境，则很难记住它代表的含义。图例表的目的包括，例如：显示每个请求在表 ID 下的名称。您还可以添加其他“图例”列，以全面了解请求。

   ![显示图例表的屏幕快照，其中显示每个请求在表 ID 下的名称。](assets/legend-table.png)
