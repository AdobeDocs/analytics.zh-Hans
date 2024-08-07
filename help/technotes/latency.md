---
description: 以下信息可帮助解决 Analytics 数据中的报表包滞后问题。
keywords: 缺少数据;缓慢
title: 数据可用性和滞后
feature: Data Configuration and Collection
exl-id: fedef3ea-dde6-460f-90e3-1e661ed29b78
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 100%

---

# Adobe Analytics 中的数据可用性和滞后

通常，收集数据后的 2 小时内即可在报表中看到完整数据。以下信息可帮助解决 Analytics 数据中的报表包滞后问题。

## 了解数据批处理

每个数据收集服务器都捕获并处理原始分析数据，然后每小时上载一次批量数据以进行报告。传输过程通常需要 30 分钟，因此上一个上载过程完成后紧接着出现的正常流量滞后约为 90 分钟（到下一次批量上载需要 60 分钟，传输并显示文件需要 30 分钟）。对于上载前出现的流量，数据滞后可能降到 30 分钟（到下一次批量上载需要 0 分钟，传输并显示文件需要 30 分钟）。

如果需要，客户关怀团队可以为您的最常用报表包启用 30 分钟批量数据上载（而不是一小时一次）。

## 滞后因素

数据收集服务器完全处理数据通常需要 2 小时，滞后是指此时间以外的延迟。滞后不影响数据收集；无论报表包滞后多长时间，仍会为正在工作的实施收集数据。其严重性（数据的当前状态）和长度（解析所花费的时间）可能差别很大。滞后通常仅限于单个报表包。

导致滞后的原因大致可分为以下几类：

* **意外的流量尖峰：**&#x200B;在发送到报表包的数据多于合同承诺或预期的数据时，会发生这种类型的滞后。这是导致滞后的最常见原因。
* **普通硬件问题：** Adobe 为数据中心管理与监控、数据冗余和硬件可靠性采用了一流的策略。我们会定期更新硬件，同时也会更新发布的维护时段。故障硬件的紧急维护期间，由于更换硬件上线，可能需要临时终止数据处理（不会终止数据收集）。这种处理过程临时终止可能会导致显著的滞后。
* **异常数据：**&#x200B;异常数据模式（如机器人或爬网程序导致访问时间过长）可能会临时增加某些处理负载，导致滞后。

## 依赖滞后的功能

Adobe Experience Cloud 中的某些功能在标准处理时间的基础上固有一定时间的延迟。

* Analytics for Target (A4T) 需要额外 5 - 10 分钟的延迟，以允许从两个平台收集的数据存储在同一次点击中。
* 时间戳数据由于处理服务器不同，因此额外需要一些时间。实时或接近实时接收的时间戳点击最长可能需要 15 分钟。收到的具有昨天时间戳的点击最长可能需要 2 小时。更早的点击可能需要更长的时间，每天最长可以增加约 24 小时。

## 缓解或防止滞后的方法

有多种策略可以防止滞后或缩短滞后发生后的恢复时间：

* **通知 Adobe 预期流量尖峰：**&#x200B;虽然不可能预测到您网站的每个流量尖峰，但有时您可能会预料到网站的流量会显著增加。例如，时间较长的假期，或大型营销活动推送后不久。在这些情况下，您的组织可以通过 Adobe 提供的方式来通知我们预期的流量增加，以便我们可以向您的报表包分配额外的处理资源。有关如何通知 Adobe 流量增加的信息，请参阅管理员用户指南中的[计划流量尖峰](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)。
* **在激活新功能时请考虑处理负载问题：**&#x200B;某些功能的处理密集度远高于其他功能。对报表包启用的功能越多，越难从滞后问题中恢复。在对报表包启用某些功能时，请注意以下功能会增加要处理的数据量：

   * 在同一页面上实施的事件超过 20 个
   * 复杂的 VISTA 规则
   * 产品变量中有超过 20 个值
   * 事件序列化

* 启用 IAB 机器人过滤：如果机器人或爬网程序经常影响报表包，则[机器人过滤](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)可以显著减少滞后。推荐使用 IAB 机器人列表，因为它是由[美国互动广告局 (Interactive Advertising Bureau) ](https://www.iab.net/about_the_iab)更新和维护的。用户可以自定义其自己的机器人规则以补充 IAB 所提供的机器人规则。

## 如何处理滞后

在出现滞后时，请确保 Adobe 会主动监控处理管道并尽可能尽快地将处理时间恢复为正常。许多滞后问题可在数小时内得到解决。如果您特别关注某个特定报表包，贵组织的某位受支持用户可以联系客户关怀团队，并提供遇到滞后的报表包 ID。Adobe 代表可以验证滞后，并在问题得到改善和解决时通知您。
