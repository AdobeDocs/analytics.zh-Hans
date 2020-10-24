---
title: 页面查看次数
description: 查看页面的次数。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '153'
ht-degree: 100%

---


# 页面查看次数

“页面查看次数”量度显示页面上设定或保留的给定维度项目的次数。它是报告中最常见的基本量度之一。

## 如何计算此量度

此量度计数报表包中所有页面视图的跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))。对于维度，它包括定义或保留维度项目的点击。它不包括链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 与类似量度比较

* **页面查看次数与[访问次数](visits.md)**：页面查看次数计算页面被查看的次数。访问次数计算访客的会话数。一次访问包含一个或多个页面。
* **页面查看次数与[页面事件数](page-events.md)**：页面查看次数计算页面视图跟踪调用 (`t()`) 的数量，不包括链接跟踪调用 (`tl()`)。页面事件数则相反；它会计算链接跟踪调用的数量，并且不包括页面查看次数。