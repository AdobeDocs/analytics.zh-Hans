---
title: 页面查看次数
description: 在 Adobe Analytics 中设置或保留维度项目的次数。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 65f87bf4b5b3897c9ef68d091858332c08cbf699
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 100%

---

# 页面查看次数

“页面查看次数”指标显示页面上设定或保留的给定维度项目的次数。它是报告中最常见的基本指标之一。

## 如何计算此量度

此指标计数报表包中所有页面视图的跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))。对于维度，它包括定义或保留维度项目的匹配。它不包括链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 与类似指标比较

* **页面查看次数与[访问量](visits.md)**：页面查看次数计算页面被查看的次数。访问量计算访问者的会话数。一次访问由一个或多个页面查看组成。
* **页面查看次数与[页面事件](page-events.md)**：页面查看次数计算页面浏览跟踪调用的数量（`t()`），不包括链接跟踪调用（`tl()`）。页面事件则相反；他们计算链接跟踪调用的数量，并排除页面查看跟踪调用。
