---
title: 页面查看次数
description: 在 Adobe Analytics 中设置或保留维度项目的次数。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 100%

---

# 页面查看次数

**[!UICONTROL 页面浏览量]**[量度](overview.md)显示了某个给定维度项在某个页面上设置或持久化的次数。它是报告中最常见的基本量度之一。

## 如何计算此量度

此指标计数报表包中所有页面视图的跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))。对于维度，它包括使得某个维度项被设置或持久化的点击。它不包括链接跟踪调用（[`tl()`](/help/implement/vars/functions/tl-method.md)）或来自[数据源](/help/import/data-sources/overview.md)的数据。

## 与类似量度比较

* **页面浏览量与[访问量](visits.md)**：页面浏览量计算的是页面被浏览的次数。访问量计算访问者的会话数。一次访问由一个或多个页面查看组成。
* **页面浏览量与[页面事件](page-events.md)**：页面浏览量计算页面浏览跟踪调用的数量（`t()`），不包括链接跟踪调用（`tl()`）。页面事件则相反；他们计算链接跟踪调用的数量，并排除页面查看跟踪调用。
