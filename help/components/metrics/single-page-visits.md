---
title: 单页访问次数（指标）
description: “页面”维度项目在访问中未更改的次数。
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 34%

---

# 单页面访问量

*此帮助页面介绍了“单页面访问量”如何作为维度使用。有关更多信息，请参阅[单页面访问量](../dimensions/single-page-visits.md)维度。*

**[!UICONTROL 单页面访问量]** [量度](overview.md)显示[页面](../dimensions/page.md)维度项目在整个访问期间仅包含单个值的访问次数。 当您想要了解短期访问次数维度，但没有设置如[[!UICONTROL 跳出次数]](bounces.md)那么严格的规则时，此量度非常有用。

## 如何计算此指标

此量度的定义依赖于[[!UICONTROL 计数重复实例]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)的项目设置：

* **[!UICONTROL 计算已启用重复实例]**：计算[!UICONTROL 页面]维度包含访问单个值的访问次数。 如果访客重新加载页面，则不符合单页面访问资格。
* **[!UICONTROL 计数已禁用的重复实例]**：计算[!UICONTROL 页面]维度在整个访问期间包含单个唯一值的访问次数。

不论“[!UICONTROL 计数重复实例]”项目设置如何，此量度都遵循以下规则：

* 如果访客触发链接跟踪调用，则访问仍符合单页面访问的条件（从所有链接跟踪调用中剥离[!UICONTROL 页面]维度）。
* 一旦[!UICONTROL 页面]维度变为第二个唯一值，访问就不再计为单个页面访问次数。

请参阅[单次存取](single-access.md)，以了解不同量度之间的比较。
