---
description: 描述如何将过滤器应用到流失报表的步骤。
title: 使用请求向导过滤流失报表
topic: Report builder
uuid: 269e900e-23bd-48d8-9bac-69e3167a9c18
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用请求向导过滤流失报表

描述如何将过滤器应用到流失报表的步骤。

此示例显示了页面流失报表。

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. 选择适当的报表包。
1. 在左侧的树视图中，选择 **[!UICONTROL Paths]** > **[!UICONTROL Page]** > **[!UICONTROL Page Fallout]**。

   ![](assets/page_fallout.png)

1. 配置相应的[日期范围](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)。
1. 单击 **[!UICONTROL Next]**.
1. 在向导的步骤2中，在下 **[!UICONTROL Row Labels]**&#x200B;面单击链 **[!UICONTROL Define Checkpoints]** 接。 （在流失报表中，您始终必须定义路径元素，这与预先应用了模式的路径报表不同。）

   ![](assets/define_checkpoints.png)

1. 选择 **[!UICONTROL Filter]** 选项。

1. 在对话 **[!UICONTROL Define Site Section Fallout Checkpoints]** 框中，从一系列单元格或列表中定义检查点。 接着，单击 **[!UICONTROL OK]**。
1. 确定从单元格范围还是列表进行选择。
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. 您可以定义 3 至 8 个检查点。(Search for available elements by clicking **[!UICONTROL More]**.)

   有关优化过滤器的更多信息，请参阅[过滤器维度](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md)。1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. 单击 **[!UICONTROL OK]** 三次，然后单击 **[!UICONTROL Finish]**。

   现在应当刷新了报表。
