---
title: Analytics 平台之间的处理和架构差异
description: 了解在 Adobe Analytics 和 Google Analytics 等平台之间数据收集和显示方式有何不同。
translation-type: ht
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analytics 平台之间的处理和架构差异

尽管 Adobe Analytics 和 Google Analytics 都是 Analytics 工具，但平台之间收集和处理数据的方式却截然不同。通过本页面可了解某些维度和量度的收集方式以及它们在类似报表中显示不同数字的原因方面的一些主要差异。

## 跳出率

“跳出率”是一种常用的 KPI，可用来帮助衡量大多数分析工具中登录页面的效率和相关性。跳出率通常定义为进入网站但不包括其他页面点击的访问。

* 在 Adobe Analytics 中，“跳出率”使用公式&#x200B;**跳出次数除以条目总数**&#x200B;来计算。
* 在 Google Analytics 中，“跳出率”使用公式&#x200B;**单页面会话次数除以会话总数**&#x200B;来计算。

在这两个平台上，如果在同一访问或会话中发送了多个点击，则不会被视为跳出。在 Adobe Analytics 中，自定义链接可用且相当常见，可阻止访问计为跳出。Google Analytics 通常不会在同一页面上发送多个数据请求。

为了在报告工具之间更好地实现同等功能，请使用 Adobe Analytics 中的“单页面访问量”量度，而不是作为计算量度一部分的“跳出次数”。“单页面访问次数”量度包括仅包含单页查看的访问总数，或进入网站但不包含其他页面点击的访问总数。

有关更多信息，请参阅组件用户指南中的[跳出率](/help/components/c-variables/c-metrics/metrics-bounce-rate.md)量度。

## 访问和会话

访问（在 Google Analytics 中称为会话）是同一用户在短时间内进行的一组页面查看。两种平台上的访问通常在非活动状态持续 30 分钟后过期。两个平台都允许在访问过期时进行自定义。有几种情况可能会导致每个平台上的差异。

* **结束日期：** Google Analytics 中的所有会话在指定日期的夜间 11:59 后过期。如果用户在午夜 12 点后仍在您的站点上处于活动状态，则会创建新会话。Adobe Analytics 将继续在同一次访问中访问到次日。
* **不同的营销活动：**&#x200B;如果用户的营销活动源发生更改，将在 Google Analytics 启动新会话。如果在 Adobe Analytics 中看到新的跟踪代码值，则该值将被视为同一访问的一部分。
* **手动会话覆盖：**&#x200B;如果您使用 `sessionControl` 手动启动或结束会话，则将在 Google Analytics 中启动新会话。在 Adobe Analytics 中，无法手动结束访问。
* **Adobe Analytics 中的异常访问检测：**&#x200B;如果用户达到 12 小时的连续活动、2500 次点击或者在 100 秒内达到 100 次点击，则将在 Adobe Analytics 中自动启动新访问。其中每个检测标准通常由机器人活动触发。

有关更多信息，请参阅组件用户指南中的[访问](/help/components/c-variables/c-metrics/metrics-visit.md)量度。
