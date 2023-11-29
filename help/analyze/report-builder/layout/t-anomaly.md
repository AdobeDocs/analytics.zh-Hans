---
description: 了解如何在Report Builder中创建异常检测请求。
title: 如何配置异常检测请求
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 72%

---

# 配置异常检测请求

要在Report Builder中创建异常检测请求，请执行以下操作：

1. 选择一个趋势报告，如&#x200B;**[!UICONTROL 网站量度]** > **[!UICONTROL 流量]**&#x200B;报告。
1. 在“[!UICONTROL 应用粒度]”菜单中，选择&#x200B;**[!UICONTROL 日]**。

   >[!NOTE]
   >
   >仅当您选择“日”粒度时，才可使用[!UICONTROL 异常检测]菜单。无论您选择什么日期范围，前 30 天的数据都会用作统计数据培训期。

1. 在配置日期范围后，单击&#x200B;**[!UICONTROL 下一步]**。

   在“请求向导: 第 2 步（共 2 步）”中，添加一个量度，如&#x200B;**[!UICONTROL 访问次数]**。

   对于添加的量度，单击&#x200B;**[!UICONTROL 无]**&#x200B;链接。

   ![屏幕截图显示了异常检测，插入，然后插入“下限”和“上限”选项以及预期选项。](assets/anomaly_select.png)

1. 选择&#x200B;**[!UICONTROL 异常检测]** > **[!UICONTROL `<selection>`]**。

   ![屏幕截图显示了“请求向导第2步 — 流量报告”。](assets/anomaly_visit.png)

   当您选择其中一个选项时，系统会创建原始量度的“异常检测”副本。例如，对于“访问”量度，系统会将“访问下限”量度添加到“[!UICONTROL 量度]”群组中。
1. 单击&#x200B;**[!UICONTROL 完成]**，并选择要输出到 Excel 中的单元格。

   请参阅[异常检测](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)以了解定义。
