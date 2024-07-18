---
title: Analytics 平台之间的处理和架构差异
description: 了解在 Adobe Analytics 和 Google Analytics 等平台之间数据收集和显示方式有何不同。
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 100%

---

# Analytics 平台之间的处理和架构差异

尽管 Adobe Analytics 和 Google Analytics 都是 Analytics 工具，但平台之间收集和处理数据的方式却截然不同。通过本页面可了解某些维度和量度的收集方式以及它们在类似报表中显示不同数字的原因方面的一些主要差异。

## [!UICONTROL 跳出率]

[!UICONTROL “跳出率”是一种常用的 KPI，可用来帮助衡量大多数分析工具中登录页面的效率和相关性。]跳出率通常定义为进入网站但不包括其他页面点击的访问。

* 在 Adobe Analytics 中，[!UICONTROL 跳出率]使用公式&#x200B;**跳出次数除以登入数**&#x200B;来计算。
* 在 Google Analytics 中，[!UICONTROL 跳出率]使用公式&#x200B;**单页面会话数除以会话数**&#x200B;来计算。

在这两个平台上，如果在同一访问或会话中发送了多个点击，则不会被视为跳出。在 Adobe Analytics 中，自定义链接可用且相当常见，可阻止访问计为跳出。Google Analytics 通常不会在同一页面上发送多个数据请求。

为了在不同的报表工具之间实现更好的等同性，在 Adobe Analytics 的计算量度中，请使用[!UICONTROL 单页面访问量]量度而非[!UICONTROL 跳出数]。[!UICONTROL 单页面访问量]量度包括仅含有单页面访问的访问总数，或者进入了网站但不包括对其他页面点击的访问数。

有关更多信息，请参阅组件用户指南中的[跳出率](/help/components/metrics/bounce-rate.md)量度。

## [!UICONTROL 访问]和会话

[!UICONTROL 访问]（在 Google Analytics 中称为会话）是由同一位用户在较短的时间里发出的一组页面查看数。两种平台上的[!UICONTROL 访问]通常在非活动状态持续 30 分钟后过期。两种平台均允许对[!UICONTROL 访问]的过期时间进行自定义。有几种情况可能会导致每个平台上的差异。

* **结束日期：** Google Analytics 中的所有会话在指定日期的夜间 11:59 后过期。如果用户在午夜 12 点后仍在您的站点上处于活动状态，则会创建新会话。Adobe Analytics 将继续在同一次访问中访问到次日。
* **不同的营销活动：**&#x200B;如果用户的营销活动源发生更改，将在 Google Analytics 启动新会话。如果在 Adobe Analytics 中看到了新的[!UICONTROL 跟踪代码]值，则会将其视为相同访问的一部分。
* **手动会话覆盖：**&#x200B;如果您使用 `sessionControl` 手动启动或结束会话，则将在 Google Analytics 中启动新会话。[!UICONTROL 在 Adobe Analytics 中，无法手动结束访问。]
* **Adobe Analytics 中的异常访问检测：**&#x200B;如果某位用户连续活动达到 12 小时、产生 2500 次点击或者 100 秒内点击了 100 次，Adobe Analytics 中将自动启动新的[!UICONTROL 访问]。其中每个检测标准通常由机器人活动触发。

有关更多信息，请参阅组件用户指南中的[访问](/help/components/metrics/visits.md)量度。
