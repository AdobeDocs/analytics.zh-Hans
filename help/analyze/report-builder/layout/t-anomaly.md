---
description: 用于描述如何在报表生成器中创建异常检测请求的步骤。
title: 配置异常检测请求
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 配置异常检测请求

用于描述如何在 Report Builder 中创建异常检测请求的步骤。

1. 选择趋势报表，如 **[!UICONTROL Site Metrics]** >报 **[!UICONTROL Traffic]** 表。
1. 在菜单 [!UICONTROL Apply Granularity] 中，选择 **[!UICONTROL Day]**。

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. 无论您选择什么日期范围，前 30 天的数据都会用作统计数据培训期。

1. After configuring date ranges, click **[!UICONTROL Next]**.

   步骤结果 1. On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   步骤结果 1. For the added metric, click the **[!UICONTROL None]** link.

   ![步骤结果](assets/anomaly_select.png)

1. 选择 **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![步骤信息](assets/anomaly_visit.png)

   当您选择其中一个选项时，系统会创建原始量度的“异常检测”副本。For example, for the Visit metric, a Lower Bound Visit metric is added to the [!UICONTROL Metric] group.
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   请参阅[异常检测](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)以了解定义。
