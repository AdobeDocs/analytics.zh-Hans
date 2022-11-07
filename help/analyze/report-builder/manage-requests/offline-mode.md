---
description: 脱机模式会返回占位符数据，从而加快创建和编辑请求的过程。
title: 用于创建和编辑请求的脱机模式
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: ht
source-wordcount: '201'
ht-degree: 100%

---

# 用于创建和编辑请求的脱机模式

脱机模式会返回占位符数据，从而加快创建和编辑请求的过程。

当您创建或编辑新请求时，会调用报告 API 以检索响应。这会减慢请求创建过程，因为您必须等待返回数据后才能继续执行下一步。脱机模式仅返回占位符数据，因此不必调用任何 API。

要启用脱机模式，请执行以下操作：

1. 单击 Report Builder 菜单中的&#x200B;**[!UICONTROL 选项]**。

   ![离线模式](assets/offline_mode.png)

1. 选中&#x200B;**[!UICONTROL 打开脱机模式以创建和编辑请求]**&#x200B;旁边的复选框。
1. 在&#x200B;**[!UICONTROL 将量度数据显示为]**&#x200B;字段中，输入要在请求中返回的占位符数据。例如，输入“1”。
1. 单击&#x200B;**[!UICONTROL 确定]**。
1. 现在，使用“请求向导”创建并运行您的请求（以脱机模式）。
1. 您的以“1”作为占位符数据的请求将与以下内容类似：

   ![离线模式示例](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >请确保禁用了“离线模式”后，再使用实际数据运行请求。 要执行此操作，只需返回至&#x200B;**[!UICONTROL 选项]**，然后移除复选标记。
