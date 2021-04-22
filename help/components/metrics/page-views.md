---
title: '页面浏览次数指标解释 | Adobe Analytics '
description: 了解如何在 Adobe Analytics 中得出页面浏览次数指标并了解页面浏览次数与访问次数之间的区别。
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---

# 了解页面浏览次数与 Adobe Analytics

“页面查看次数”指标显示页面上设定或保留的给定维度项目的次数。它是报告中最常见的基本指标之一。

## 如何计算此量度

此指标计数报表包中所有页面视图的跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))。对于维度，它包括定义或保留维度项目的点击。它不包括链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 与类似指标比较

* **页面查看次数与[访问次数](visits.md)**：页面查看次数计算页面被查看的次数。访问次数计算访客的会话数。一次访问包含一个或多个页面。
* **页面查看次数与[页面事件数](page-events.md)**：页面查看次数计算页面视图跟踪调用 (`t()`) 的数量，不包括链接跟踪调用 (`tl()`)。页面事件数则相反；它会计算链接跟踪调用的数量，并且不包括页面查看次数。
