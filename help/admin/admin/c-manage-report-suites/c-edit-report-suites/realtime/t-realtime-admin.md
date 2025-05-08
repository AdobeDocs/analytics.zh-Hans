---
description: 设置实时报表的管理步骤。
title: 实时报表配置
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 76%

---

# 实时报表配置

设置实时报表的管理步骤。

在Adobe Analytics中设置实时报表包括选择报表包并为其配置至多3个报表。 默认情况下，所有用户均有权访问实时报表。

1. 选择您要为其启用实时报表的报表包。

   导航至&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL 管理员>报表包]**。

1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 实时]**。

1. 为至多 3 个表报设置实时数据收集，每个报表具有 1 个量度和 3 个维度或分类。

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   有关受支持的实时量度和维度的信息，请参阅[受支持的量度和维度](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)。

   如果已创建了分类，则分类会缩进显示在其所定义的维度下。

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >对于单个实时报表，目前不支持启用重复维度，即使为每个维度选择不同分类也是如此。

   >[!NOTE]
   >
   >某些维度（例如“搜索关键词”或“产品”）在实时报表中并非持续存在，这一点与 Adobe Analytics 中的其他位置不同。当选择非持续量度时，会出现以下警告：

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

   在初始报表设置中，最多需要 20 分钟数据才会开始传输。从那时起，数据立即可用。

1. 要查看实时报表，请导航至：

   **[!UICONTROL Workspace]** > **[!UICONTROL 报表]** > **[!UICONTROL 参与度]** > **[!UICONTROL 实时]**。

