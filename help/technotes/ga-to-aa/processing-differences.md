---
title: Analytics 平台之间的处理和架构差异
description: 了解在 Adobe Analytics 和 Google Analytics 等平台之间数据收集和显示方式有何不同。
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 66%

---


# Analytics 平台之间的处理和架构差异

尽管 Adobe Analytics 和 Google Analytics 都是 Analytics 工具，但平台之间收集和处理数据的方式却截然不同。通过本页面可了解某些维度和量度的收集方式以及它们在类似报表中显示不同数字的原因方面的一些主要差异。

## [!UICONTROL 跳出率]

[!UICONTROL “跳出率”是一种常用的 KPI，可用来帮助衡量大多数分析工具中登录页面的效率和相关性。]跳出率通常定义为进入网站但不包括其他页面点击的访问。

* In Adobe Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Single-page sessions divided by Sessions**.

在这两个平台上，如果在同一访问或会话中发送了多个点击，则不会被视为跳出。在 Adobe Analytics 中，自定义链接可用且相当常见，可阻止访问计为跳出。Google Analytics 通常不会在同一页面上发送多个数据请求。

To achieve better parity between reporting tools, use the [!UICONTROL Single Page Visits] metric in Adobe Analytics instead of [!UICONTROL Bounces] as part of a calculated metric. The [!UICONTROL Single Page Visits] metric includes the total number of visits that only included one-page view, or visits that enter the website but do not include a click to another page.

有关更多信息，请参阅组件用户指南中的[跳出率](/help/components/c-variables/c-metrics/metrics-bounce-rate.md)量度。

## [!UICONTROL 访问和会话]

[!UICONTROL 访问] （在Google Analytics中称为会话）是同一用户在短时间内创建的一组页面视图。 [!UICONTROL 两种平台上的访问通常在非活动状态持续 30 分钟后过期。]Both platforms allow customization on when a [!UICONTROL Visit] expires. 有几种情况可能会导致每个平台上的差异。

* **结束日期：** Google Analytics 中的所有会话在指定日期的夜间 11:59 后过期。如果用户在午夜 12 点后仍在您的站点上处于活动状态，则会创建新会话。Adobe Analytics 将继续在同一次访问中访问到次日。
* **不同的营销活动：**&#x200B;如果用户的营销活动源发生更改，将在 Google Analytics 启动新会话。If a new [!UICONTROL Tracking Code] value is seen in Adobe Analytics, it is considered part of the same visit.
* **手动会话覆盖：**&#x200B;如果您使用 `sessionControl` 手动启动或结束会话，则将在 Google Analytics 中启动新会话。[!UICONTROL 在 Adobe Analytics 中，无法手动结束访问。]
* **Adobe Analytics中的异常访问检测：** 如果用 [!UICONTROL 户在] 100秒内连续活动12小时、点击2500次或点击100次，Adobe Analytics中的新“访问”会自动进行开始。 其中每个检测标准通常由机器人活动触发。

有关更多信息，请参阅组件用户指南中的[访问](/help/components/c-variables/c-metrics/metrics-visit.md)量度。
