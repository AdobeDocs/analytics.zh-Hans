---
title: Analytics平台之间的处理和架构差异
description: 了解在Adobe Analytics和Google Analytics等平台之间收集和显示部分数据的方式。
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Analytics平台之间的处理和架构差异

尽管Adobe Analytics和Google Analytics都是Analytics工具，但是在平台之间收集和处理数据的方式截然不同。使用本页了解某些维度和指标的收集方式以及为何在类似报告中显示不同数字的原因。

## 跳出率

跳出率是常用KPI，用于帮助测量大多数分析工具中着陆页面的有效性和相关性。通常定义为进入网站但不包括点击其他页面的访问。

* In Adobe Analytics, Bounce Rate is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, Bounce Rate is calculated using the formula **Single-page sessions divided by Sessions**.

在这两种平台上，如果在同一访问或会话中发送多次点击，则不会被视为退回。在Adobe Analytics中，自定义链接可用并且相当常见，这可以防止访问次数计为退回。Google Analytics通常不会在同一页面上发送多个数据请求。

为了实现报表工具之间的更好平衡，请使用Adobe Analytics中的“单页访问”量度，而不是作为计算量度的一部分进行跳出。“单页访问”量度包括仅包含一次页面查看次数的访问总数，或进入网站但不包括点击其他页面的访问总数。

See the [Bounce Rate](../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for more information.

## 访问和会话

访问(称为Google Analytics中的会话)是同一用户在短时间内制作的一组页面查看。在不活动的30分钟后，这两个平台上的访问通常会过期。这两个平台都允许在访问过期时自定义。有若干情景可能会在每个平台上造成差异。

* **结束日期：** Google Analytics中的所有会话在指定日期11：59PM之后过期。如果用户在12AM之后仍处于活动状态，则会创建新会话。Adobe Analytics将在同一访问中继续访问下一天。
* **不同的营销活动：** 如果用户的营销活动源发生变化，则Google Analytics中的新会话开始。如果在Adobe Analytics中看到了新的跟踪代码值，则会被视为同一访问的一部分。
* **手动会话覆盖：** 如果您使用 `sessionControl` 手动启动或结束会话，Google Analytics中的新会话开始。无法在Adobe Analytics中手动结束访问。
* **Adobe Analytics中的异常访问检测：** 如果用户在100秒内触及12小时持续活动、2500次点击或100次点击，Adobe Analytics中的新访问将自动开始。每个检测条件通常由机器人活动触发。

See the [Visits](../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for more information.
