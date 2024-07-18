---
title: 单页访问次数（指标）
description: “页面”维度项目在访问中未更改的次数。
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 86%

---

# 单页面访问量

*此帮助页面介绍了“单页面访问量”如何作为维度使用。有关更多信息，请参阅[单页面访问量](../dimensions/single-page-visits.md)维度。*

[!UICONTROL 单页面访问量] [量度](overview.md)显示[页面](../dimensions/page.md)维度项目在整个访问期间仅包含单个唯一值的访问次数。 当您想要了解短期访问次数维度，但没有设置如[[!UICONTROL 跳出次数]](bounces.md)那么严格的规则时，此量度非常有用。

## 如何计算此量度

此量度计算[!UICONTROL 页面]维度项目在整个访问期间仅包含单个唯一值的访问次数。如果访客重新加载页面或触发链接跟踪调用，仍将其计为“单个页面访问次数”。“页面”维度一旦变为第二个唯一值，访问就不再计为单个页面访问次数。

请参阅[单次存取](single-access.md)，以了解不同量度之间的比较。

## 计数重复实例

此设置指定是否将重复实例计入报表中。有关更多信息，请参阅[计算重复实例](/help/components/metrics/count-repeat-instances.md)。
