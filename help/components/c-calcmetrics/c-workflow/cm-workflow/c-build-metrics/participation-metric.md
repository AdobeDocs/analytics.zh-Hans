---
description: 借助计算量度生成器，任何人都可以创建参与量度。
title: 参与率量度
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 34%

---

# 构建“参与率”量度

以下信息介绍了如何创建一个量度，以显示哪些页面促成了（或参与了）包含订单的访问。

此类信息对任何内容所有者都很有用。

>[!NOTE]
>
>您可以在管理工具中启用参与率量度，但仅限于自定义事件1 - 100。

1. 开始创建计算指标，如中所述 [生成量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. 在计算量度生成器中，将量度命名为“参与率”。

1. 将成功事件“订购”拖到“定义”画布。

1. 在[设置](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)齿轮下，将该事件的&#x200B;**[!UICONTROL 归因模型]**&#x200B;更改为&#x200B;**[!UICONTROL 参与率]**。选择&#x200B;**[!UICONTROL 访问]**&#x200B;回顾窗口。定义应该类似于：

   ![](assets/participation.png)

1. 选择 [!UICONTROL **保存**] 以保存指标。

1. 在&#x200B;**[!UICONTROL 页面]**&#x200B;报表中使用计算量度。

   ![](assets/participation-pages.png)

1. （可选）与组织中的其他用户共享量度，如中所述 [共享计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
