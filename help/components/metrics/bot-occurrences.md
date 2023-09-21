---
title: 机器人发生次数
description: 与机器人规则匹配的点击数。
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# 机器人发生次数

“机器人出现次数” [量度](overview.md) 显示匹配的点击数 [机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

由于机器人报表与报表包的其他数据是分开的，因此此量度仅适用于以下维度：

* [机器人名称](../dimensions/bot-name.md)
* [页面](../dimensions/page.md)
* 基于时间的维度(例如， [天](../dimensions/day.md)， [周](../dimensions/week.md)，或 [月](../dimensions/month.md))

将任何其他维度与此量度一起使用不会返回数据。

## 如何计算此指标

Adobe会检查每次点击，查看它是否与贵组织配置的机器人规则匹配。 如果给定的点击与机器人规则匹配，则该点击将从报表中排除，并且此量度将增加1。 此量度包含两个页面查看次数([`t()`](/help/implement/vars/functions/t-method.md))和链接跟踪点击([`tl()`](/help/implement/vars/functions/tl-method.md))，而 [机器人页面查看次数](bot-page-views.md) 不包括链接跟踪点击。
