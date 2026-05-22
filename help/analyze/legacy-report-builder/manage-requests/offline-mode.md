---
description: 了解如何使用离线模式返回占位符数据。
title: 如何启用离线模式
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 12%

---

# 用于创建和编辑请求的脱机模式

{{legacy-arb}}

脱机模式会返回占位符数据，从而加快创建和编辑请求的过程。

创建或编辑新请求时，会调用报表API以检索响应。 有时，这些调用会减慢请求创建过程的速度，因为您必须等待数据返回后再执行下一步。 脱机模式仅返回占位符数据，不会生成API。

启用脱机模式

1. 在Report Builder菜单中单击&#x200B;**[!UICONTROL 选项]**。

   ![已选择脱机代码的“选项”屏幕截图。](assets/offline_mode.png)

1. 选中&#x200B;**[!UICONTROL 启用脱机模式以创建和编辑请求]**&#x200B;旁边的复选框。
1. 在&#x200B;**[!UICONTROL 将量度数据显示为]**&#x200B;字段中，输入要在请求中返回的占位符数据。 例如，输入“1”。
1. 单击&#x200B;**[!UICONTROL 确定]**。
1. 使用“请求向导”在脱机模式下创建并运行请求。 以下屏幕截图显示了将“1”作为占位符数据的请求示例。

   ![显示使用1作为占位符的脱机模式示例的屏幕截图。](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >请确保禁用了“脱机模式”后，再使用实际数据运行请求。
