---
title: Analytics平台之间的处理和架构差异
description: 了解某些数据的收集和显示方式在Adobe Analytics和Google Analytics等平台之间是如何不同的。
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analytics平台之间的处理和架构差异

尽管Adobe Analytics和Google Analytics都是Analytics工具，但在不同平台之间收集和处理数据的方式却截然不同。 使用本页可了解某些维度和指标的收集方式以及它们在类似报告中显示不同数字的原因方面的一些主要差异。

## 跳出率

跳出率是常用的KPI，用于帮助评估大多数分析工具中登录页面的有效性和相关性。 这通常定义为进入网站但不包括单击其他页面的访问。

* 在Adobe Analytics中，弹出率是使用公式弹出次数除以 **条目来计算的**。
* 在Google Analytics中，弹出率是使用公式单页会 **话除以会话计算的**。

在两个平台上，如果在同一访问或会话中发送了多个点击，则不会被视为跳出。 在Adobe Analytics中，自定义链接可用且相当常见，这会阻止访问计为退回。 Google Analytics通常不会在同一页面上发送多个数据请求。

为了更好地实现报告工具之间的对等性，请使用Adobe Analytics中的“单页访问量”量度，而不要将“弹回次数”作为计算量度的一部分。 “单页访问”量度包括仅包含单页查看的访问总数，或进入网站但不包含单击其他页面的访问总数。

有关详细 [信息，请参阅组件用户指南中的](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) “跳出率”量度。

## 访问和会话

访问（在Google Analytics中称为会话）是同一用户在短时间内进行的一组页面查看。 两种平台上的访问通常在非活动状态持续30分钟后过期。 两个平台都允许在访问过期时进行自定义。 有几种情况可能会导致每个平台上的差异。

* **** 结束日期：Google Analytics中的所有会话在指定日的晚上11:59后过期。 如果用户在上午12点后仍在您的站点上处于活动状态，则会创建新会话。 作为同一次访问的一部分，Adobe Analytics将继续访问到次日。
* **** 不同的营销活动：如果用户的营销活动源发生更改，Google Analytics中的新会话将启动。 如果在Adobe Analytics中看到新的跟踪代码值，则该值将被视为同一访问的一部分。
* **** 手动会话覆盖：如果您使用手动启动或结束会话，Google Analytics `sessionControl` 中将启动新会话。 在Adobe Analytics中，无法手动结束访问。
* **** Adobe Analytics中的异常访问检测：如果用户在100秒内达到12小时的连续活动、2500次点击或100次点击，则Adobe Analytics中的新访问将自动开始。 这些检测标准中的每个通常由机器人活动触发。

有关详细 [信息](/help/components/c-variables/c-metrics/metrics-visit.md) ，请参阅组件用户指南中的访问量度。
