---
description: 用于描述如何在报表生成器中创建异常检测请求的步骤。
title: 配置异常检测请求
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 配置异常检测请求

用于描述如何在 Report Builder 中创建异常检测请求的步骤。

1. 选择一个趋势报表，如&#x200B;**[!UICONTROL 网站量度]** > **[!UICONTROL 流量]**&#x200B;报表。
1. 在“[!UICONTROL 应用粒度]”菜单中，选择&#x200B;**[!UICONTROL 日]**。

   >[!NOTE]
   >
   >仅当您选择“日”粒度时，才可使用[!UICONTROL 异常检测]菜单。无论您选择什么日期范围，前 30 天的数据都会用作统计数据培训期。

1. 在配置日期范围后，单击&#x200B;**[!UICONTROL 下一步]**。

   步骤结果 1. 在“请求向导: 第 2 步（共 2 步）”中，添加一个量度，如&#x200B;**[!UICONTROL 访问次数]**。

   步骤结果 1. 对于添加的量度，单击&#x200B;**[!UICONTROL 无]**&#x200B;链接。

   ![步骤结果](assets/anomaly_select.png)

1. 选择&#x200B;**[!UICONTROL 异常检测]** > **[!UICONTROL `<selection>`]**。

   ![步骤信息](assets/anomaly_visit.png)

   当您选择其中一个选项时，系统会创建原始量度的“异常检测”副本。例如，对于“访问”量度，系统会将“访问下限”量度添加到“[!UICONTROL 量度]”群组中。
1. 单击&#x200B;**[!UICONTROL 完成]**，并选择要输出到 Excel 中的单元格。

   请参阅[异常检测](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)以了解定义。
