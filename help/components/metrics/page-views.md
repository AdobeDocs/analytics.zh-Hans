---
title: 页面查看次数
description: 在 Adobe Analytics 中设置或保留维度项目的次数。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 63%

---

# 页面查看次数

此 **[!UICONTROL 页面查看次数]** 量度显示页面上定义或保留的给定维度项目（维度值）的次数（即其过期时间）。 它是报告中最常见的基本指标之一。

例如， [!UICONTROL 每周天数] 维度由以下维度项目组成：星期日、星期一、星期二、星期三、星期四、星期五和星期六。

## 如何计算此量度

此指标计数报表包中所有页面视图的跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))。对于维度，它包括定义或保留维度项目的匹配。它不包括链接跟踪调用([`tl()`](/help/implement/vars/functions/tl-method.md))或摘要中的数据 [数据源](/help/import/data-sources/overview.md).

## 与类似指标比较

* **页面查看次数与[访问量](visits.md)**：页面查看次数计算页面被查看的次数。访问量计算访问者的会话数。一次访问可以包含一个或多个页面查看。
* **页面查看次数与[页面事件](page-events.md)**：页面查看次数计算页面浏览跟踪调用的数量（`t()`），不包括链接跟踪调用（`tl()`）。页面事件则相反；他们计算链接跟踪调用的数量，并排除页面查看跟踪调用。
