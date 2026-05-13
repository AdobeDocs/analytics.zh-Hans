---
description: 设置实时报表的管理步骤。
title: 实时报表配置
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 68%

---

# 实时报表配置

设置实时报表的管理步骤。

在Adobe Analytics中设置实时报表包括选择报表包并为其配置至多3个报表。 默认情况下，所有用户均有权访问实时报表。

1. 选择您要为其启用实时报表的报表包。

   导航至&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL 管理员>报表包]**。

1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 实时]**。

1. 为至多 3 个表报设置实时数据收集，每个报表具有 1 个量度和 3 个维度或分类。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   有关受支持的实时量度和维度的信息，请参阅[受支持的量度和维度](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md)。

   如果已创建了分类，则分类会缩进显示在其所定义的维度下。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >对于单个实时报表，目前不支持启用重复维度，即使为每个维度选择不同分类也是如此。

   >[!NOTE]
   >
   >某些维度（例如“搜索关键词”或“产品”）在实时报表中并非持续存在，这一点与 Adobe Analytics 中的其他位置不同。 当选择非持续量度时，会出现以下警告：

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

   初次设置报表后，可能需要20分钟才能开始流式传输数据。 从那时起，数据立即可用。

1. 要查看实时报表，请导航至：

   **[!UICONTROL Workspace]** > **[!UICONTROL 报表]** > **[!UICONTROL 参与度]** > **[!UICONTROL 实时]**。

