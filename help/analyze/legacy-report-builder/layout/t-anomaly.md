---
description: 了解如何在Report Builder中创建异常检测请求。
title: 如何配置异常检测请求
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
TQID: https://experienceleague.adobe.com/9qyfB3mtj7QKDNLL1PRrQ2-3lzrb19-7gL4rnfxbph4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: c67272a6-888e-425e-9e97-a87304637eed
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 54%

---

# 配置异常检测请求

{{legacy-arb}}

要在Report Builder中创建异常检测请求，请执行以下操作：

1. 选择一个趋势报告，如&#x200B;**[!UICONTROL 网站量度]** > **[!UICONTROL 流量]**&#x200B;报告。
1. 在“[!UICONTROL 应用粒度]”菜单中，选择&#x200B;**[!UICONTROL 日]**。

   >[!NOTE]
   >
   >仅当您选择“日”粒度时，才可使用[!UICONTROL 异常检测]菜单。 无论您选择什么日期范围，前 30 天的数据都会用作统计数据培训期。

1. 在配置日期范围后，单击&#x200B;**[!UICONTROL 下一步]**。

   在“请求向导: 第 2 步（共 2 步）”中，添加一个量度，如&#x200B;**[!UICONTROL 访问次数]**。

   对于添加的量度，单击&#x200B;**[!UICONTROL 无]**&#x200B;链接。

   ![显示异常检测的屏幕截图，接着插入，然后插入上下限和预期值的选项。](assets/anomaly_select.png)

1. 选择&#x200B;**[!UICONTROL 异常检测]** > **[!UICONTROL `<selection>`]**。

   ![屏幕截图显示请求向导第2步 — 流量报告。](assets/anomaly_visit.png)

   选择其中一个选项时，系统会创建原始量度的异常检测副本。 例如，对于“访问”量度，下限访问量度将添加到[!UICONTROL 量度]组中。
1. 单击&#x200B;**[!UICONTROL 完成]**，并选择要输出到 Excel 中的单元格。

   请参阅[异常检测](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)以了解定义。
