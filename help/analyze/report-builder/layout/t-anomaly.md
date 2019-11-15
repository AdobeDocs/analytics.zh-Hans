---
description: 用于描述如何在报表生成器中创建异常检测请求的步骤。
solution: Analytics
title: 配置异常检测请求
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 配置异常检测请求

用于描述如何在 Report Builder 中创建异常检测请求的步骤。

1. 选择一个趋势报表，如&#x200B;**网站量度** &gt; **[!UICONTROL 流量]**&#x200B;报表。
1. In the [!UICONTROL Apply Granularity] menu, select **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. 无论您选择什么日期范围，前 30 天的数据都会用作统计数据培训期。

1. After configuring date ranges, click **[!UICONTROL Next]**.

   步骤结果 1. On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   步骤结果 1. For the added metric, click the **[!UICONTROL None]** link.

   ![步骤结果](assets/anomaly_select.png)

1. Select **[!UICONTROL Anomaly Detection]** &gt; **[!UICONTROL `<selection>`]**.

   ![步骤信息](assets/anomaly_visit.png)

   当您选择其中一个选项时，系统会创建原始量度的“异常检测”副本。例如，对于“访问”量度，系统会将“访问下限”量度添加到“[!UICONTROL 量度]”群组中。
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   See [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) for definitions.
