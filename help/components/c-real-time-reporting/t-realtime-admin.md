---
description: 设置实时报表的管理步骤。
title: 配置实时报表
topic: Admin tools
uuid: a2c3c515-55f2-4c64-ac92-a86d75e78a86
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 配置实时报表

设置实时报表的管理步骤。

在 [!UICONTROL Reports &amp; Analytics] 中设置实时报表包括选择报表包并为其配置至多 3 个报表。

1. 选择您要为其启用实时报表的报表包。

   导航至 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 报表]** &gt; **[!UICONTROL 查看所有报表 &gt; 网站量度]** &gt; **[!UICONTROL 实时]**，然后从顶部的下拉列表中选择报表包：

   ![](assets/report_suite_selector.png)

   如果某个报表包未设置实时报表功能，而您尝试查看该报表包的实时报表，则会显示一条消息，让您设置该报表包。

   ![](assets/rep_suite_not_set_up.png)

1. 单击&#x200B;**[!UICONTROL 配置]**（齿轮图标）以运行[!UICONTROL 报表包管理器]。

   （也可以通过 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员 &gt; 报表包]** &gt; **[!UICONTROL 编辑设置]** &gt; **[!UICONTROL 实时]**&#x200B;获取。）

1. 打开&#x200B;**[!UICONTROL 启用实时设置]**。
1. 为至多 3 个表报设置实时数据收集，每个报表具有 1 个量度和 3 个维度或分类。

   ![](assets/real_time_admin.png)

   有关受支持的实时量度和维度的信息，请参阅[受支持的量度和维度](/help/components/c-real-time-reporting/realtime-metrics.md)。

   如果已创建了分类，则分类会缩进显示在其所定义的维度下。

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >对于单个实时报表，目前不支持启用重复维度，即使为每个维度选择不同分类也是如此。

   有关分类的详细信息，请参阅[关于分类](/help/components/c-classifications2/c-classifications.md)。

   >[!NOTE]
   >
   >某些维度（例如“搜索关键词”或“产品”）在实时报表中并非持续存在，这一点与 Adobe Analytics 中的其他位置不同。当选择非持续量度时，会出现以下警告：

   ![](assets/warning_dimensions.png)

1. 单击&#x200B;**[!UICONTROL 保存]**&#x200B;或&#x200B;**[!UICONTROL 保存并查看报表]**。

   在初始报表设置中，最多需要 20 分钟数据才会开始传输。之后，数据会立即可用。有关查看实时报表的信息，请参阅[运行实时报表](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html)。

1. 默认情况下，所有用户均有权访问实时报表。
