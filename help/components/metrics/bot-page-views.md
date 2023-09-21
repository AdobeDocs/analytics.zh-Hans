---
title: 机器人页面查看次数
description: 与机器人规则匹配的页面查看次数。
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# 机器人页面查看次数

“机器人页面查看次数” [量度](overview.md) 显示匹配的页面点击数 [机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

由于机器人报表与报表包的其他数据是分开的，因此此量度仅适用于以下维度：

* [机器人名称](../dimensions/bot-name.md)
* [页面](../dimensions/page.md)
* 基于时间的维度(例如， [天](../dimensions/day.md)， [周](../dimensions/week.md)，或 [月](../dimensions/month.md))

将任何其他维度与此量度一起使用不会返回数据。

## 如何计算此指标

Adobe会检查每次页面点击，查看它是否与贵组织配置的机器人规则匹配。 如果给定点击与机器人规则匹配，则页面点击将从报表中排除，并且此量度将增加1。 此量度不包括链接跟踪点击([`tl()`](/help/implement/vars/functions/tl-method.md))。
