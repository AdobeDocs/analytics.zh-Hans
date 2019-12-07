---
description: 在访客资料与同一访客 ID 变量关联后进行合并时，历史数据集中的属性不会发生更改。
keywords: Analytics Implementation
title: 属性和永久性
topic: Developer and implementation
uuid: 5dd706be-83f6-498a-a856-e3c5af995348
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 属性和永久性

> [!IMPORTANT]不再建议使用这种方法来识别跨设备访客。请参 [阅组件用户指南中](/help/components/cda/cda-home.md) 的跨设备分析。

在访客资料与同一访客 ID 变量关联后进行合并时，历史数据集中的属性不会发生更改。

* When the variable `s.visitorID` is set and sent on a hit, Adobe checks for any other visitor profiles that have a matching visitor ID.
* 如果存在，则从此时开始使用系统中存在的该访客资料，而不再使用之前的访客资料。
* 如果找不到匹配的访客 ID，则会创建一个新资料。

当未验证的客户首次到达您的网站时，Adobe Analytics 会为该客户分配一个访客资料。创建新资料后，一次访问结束，另一次访问开始。

## 示例 1

以下示例演示了当客户在第一台设备上首次进行身份验证时，如何将数据发送到Adobe Analytics:

* `eVar16` 的有效期限为 1 天，而 `evar17` 在访问时过期。
* `post_visitor_id` 列表示由 Adobe Analytics 维护的资料。帖子列通常显示在数据源中。 请参 [阅“导出](/help/export/analytics-data-feed/data-feed-overview.md) ”用户指南中的数据源。
* `post_evar16` 和 `post_evar17` 列显示 eVar 的永久性。
* `cust_visid` 表示 `s.visitorID` 中设置的值。
* 每一行就是一次“点击”，即发送到 Adobe Analytics 数据收集服务器的一个请求。

![跨设备示例1](assets/xdevice_first.jpg)

On the first data connection containing a previously unrecognized `s.visitorID` value (`u999` above), a new profile is created. 之前资料中的永久性值将会转移到新资料中。

* 设置为访问时过期的 eVar 不会复制到经验证的资料中。请注意，不会保留上述值 `car`。
* 设置为通过其他措施过期的 eVar 将会复制到经验证的资料中。请注意，将会保留值 `apple`。
* 对于保留的 eVar，不会记录实例量度。这意味着在使用跨设备访客识别时，可能会看到 eVar 值的“独特访问”量度大于“实例”量度的报表。

> [!NOTE] 如果用户不熟悉您的站点（在此设备上从未访问过），并在大约3分钟内进行身份验证，则验证后的配置文件不会保留任何值。

## 示例 2

以下示例演示了客户在先前在其他设备上通过身份验证后，在新设备上进行身份验证时，如何将数据发送到Adobe Analytics。

![跨设备示例2](assets/xdevice-subsequent.jpg)

当客户进行身份验证时，他们将与之前的“已验证”配置文件相匹配- `2947539300`。 将不再使用此次访问开始时所用的资料 (`5477766334477`)，而且不会保留该文件中的任何数据。

* 地域划分数据根据访问的首次点击进行记录，并且无论使用的是什么设备，单次访问的地域划分数据都不会更改。这意味着在新设备上进行后续数据连接时，通常不包括地域划分数据。
* 浏览器、操作系统和颜色深度等技术列将根据访问的首次点击进行记录。与“地理分段”值一样，这些值不会复制到拼接配置文件中。
* 营销渠道会覆盖后续数据连接上的其他渠道，该连接包含该设备的第一个身份验证。
