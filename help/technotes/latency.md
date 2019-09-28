---
description: The following information can help troubleshoot report suite latency issues in Analytics data.
keywords: 缺失数据；慢
seo-description: The following information can help troubleshoot report suite latency issues in Analytics data.
seo-title: Data availability and latency
solution: Analytics
subtopic: 当前数据
title: Data availability and latency
topic: 报告
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Data availability and latency in Adobe Analytics

通常，在收集数据后2小时内，您会在报告中看到完整的数据。 以下信息有助于解决Analytics数据中的报表包延迟问题。

## Understanding data batching

每个数据收集服务器都捕获并处理原始分析数据，然后每小时上载一次批量数据以进行报告。传输过程通常需要 30 分钟，因此上一个上载过程完成后紧接着出现的正常流量滞后约为 90 分钟（到下一次批量上载需要 60 分钟，传输并显示文件需要 30 分钟）。对于在上传之前直接发生的流量，数据延迟可能会短到30分钟（在下一次批量上传之前0分钟，然后为文件传输和显示30分钟）。

If needed, Adobe Customer Care can enable 30 minute batched data uploads (instead of hourly) for your most-used report suites.

## 延迟贡献者

滞后时间比数据收集服务器完全处理数据所需的典型2小时长。 它不影响数据收集；仍会为正在工作的实施收集数据，而不管报表包有多大潜在。 其严重性（数据的当前状态）和长度（解析所花费的时间）可能相差很大。 它通常仅限于单个报告套件。

导致滞后的原因大致可分为以下几类：

* **** 意外的流量尖峰：当向报表包发送的数据比按照合同约定或预期的数据多时，会出现此类延迟。 这是导致滞后的最常见原因。
* **** 正常硬件问题：Adobe在数据中心管理和监控、数据冗余和硬件可靠性方面采用一流的战略。 我们会定期更新硬件，同时也会更新发布的维护时段。故障硬件的紧急维护可能需要在数据处理（而非数据收集）中临时停止，因为更换硬件已联机。 这种处理过程临时终止可能会导致显著的滞后。
* **** 异常数据：非自然的数据模式（如由机器人或爬虫引起的异常长的访问）可能会临时增加某些导致延迟的处理负载。

## 依赖延迟的功能

Adobe Experience cloud中的某些功能在标准处理时间的基础上具有先天的延迟。

* Analytics for Target(A4T)需要额外5-10分钟的延迟，以允许从两个平台收集的数据存储在同一次点击中。
* 时间戳数据需要额外的时间，因为处理这些数据的服务器不同。 实时或接近实时接收的时间戳点击最长可能需要15分钟。 以昨天的时间戳收到的点击最多可能需要2小时。 较旧的点击可能需要更长的时间，每天最多可以增加约24小时。

## 减轻或防止延迟的方法

有多种策略可以防止滞后或缩短滞后发生后的恢复时间：

* **** 预期流量高峰时通知Adobe:虽然不可能预测到您网站的每个流量尖峰，但有时您可能希望网站的流量会显着增加。 例如，特别成功的假期，或大型营销活动推送后不久。 在这些情况下，您的组织可以通过 Adobe 提供的方式来通知我们预期的流量增加，以便我们可以向您的报表包分配额外的处理资源。请参 [阅管理员用户指南中的计划流量尖峰](../admin/c-traffic-management/t-traffic-schedule-spike.md) ，了解如何向Adobe通知流量增加。
* **** 激活新功能时，请考虑处理负载：某些功能的处理密集度高于其他功能。 对报表包启用的功能越多，越难从滞后问题中恢复。在对报表包启用某些功能时，请注意以下功能会增加要处理的数据量：

   * 在同一页面上实施20多个活动
   * 复杂的 VISTA 规则
   * 产品变量中有超过 20 个值
   * 事件序列化

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/c_bot_rules.html) can greatly reduce latency if your report suite is frequented by bots or crawlers. 推荐使用 IAB 机器人列表，因为它是由[美国互动广告局 (Interactive Advertising Bureau) ](https://www.iab.net/about_the_iab)更新和维护的。用户可以自定义自己的机器人规则，以补充IAB的规则。

## 如何处理滞后

在出现延迟时，请确保Adobe会主动监控处理管道并尽可能尽快将处理时间恢复为正常。 许多滞后问题可在数小时内得到解决。如果您特别关注某个特定报表包，贵组织的某位受支持用户可以联系客户关怀团队，并提供遇到滞后的报表包 ID。Adobe 代表可以验证滞后，并在问题得到改善和解决时通知您。
