---
title: 跟踪代码
description: 跟踪代码或营销活动的名称。
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 66%

---

# 跟踪代码

“跟踪代码”[维度](overview.md)列出了您网站上的跟踪代码的名称。 您可以将具有不同查询字符串参数值的链接放在 Internet 的不同位置。此维度可帮助您了解哪些链接最能成功吸引流量访问您的网站。

附加跟踪代码查询字符串在电子邮件、广告、社交媒体帖子以及您的组织使用的其他营销工作中很常见。

## 使用数据填充此维度

此维度从图像请求中的 [`v0` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用 [`campaign`](/help/implement/vars/page-vars/campaign.md) 变量收集此数据。

## 维度项目

维度项目包括您的网站上的跟踪代码的名称。贵组织会确定您要使用的具体维度项目。有关详细信息，请参阅[促销活动跟踪](/help/implement/use-cases/campaign-tracking.md)。

## 比较跟踪代码维度与收集跟踪代码的营销渠道

一些设置营销渠道处理规则的用户会配置一项规则，该规则采用跟踪代码维度中使用的所有值。尽管这是一种不错的做法，但是由于固有的处理和架构差异，导致这两个维度有所不同。以下列表说明了为何这两种方法虽然乍一看上去很相似，但却可以更改归因行为。

### 处理规则中的优先渠道

在列表中排名较高的营销渠道处理规则可能会阻止点击归因于“跟踪代码”营销渠道。 例如：

1. 您将“社交网络”设置为第一个规则，并将“跟踪代码”设置为第二个规则。
2. 假设用户在社交媒体网站上发布了一个指向您的网站的链接，其中包含跟踪代码，然后用户的几个朋友点击了指向您的网站的链接。

那么由于“社交网络”是第一个营销渠道处理规则，因此这些用户将归因于“社交网络”营销渠道，而不是“跟踪代码”营销渠道。

### 其他营销渠道可以通过最近联系进行归因

处理标准的跟踪代码维度时，您无需担心网站的其他部分会盗用归因。 但是，使用营销渠道，用户可以匹配不同的规则，从而提供不同的归因。例如：

1. 您将“跟踪代码”设置为第一个渠道，并将“直接”设置为第二个渠道。
2. 用户最初通过跟踪代码到达您的网站，但随后离开。
3. 第二天，他们将您网站的 URL 键入地址栏，然后购买了商品。

在本例中，跟踪代码营销渠道不会获得该购买的上次接触点数。 相反，点数会计入“直接”营销渠道。


### 到期时间差异

营销渠道具有连续30天的访客参与到期时限，无论是否接触了渠道。 而跟踪代码的到期时间则取决于变量的设置时间。例如：

1. 您的访客参与到期期限为 30 天，并且还将“跟踪代码”维度配置为在 30 天之后到期。
2. 用户通过跟踪代码到达您的网站。他们浏览网站，然后离开。
3. 三周后，他们重新访问网站且没有使用跟踪代码或营销渠道，然后再次离开。
4. 又过了两周后（自最初访问经过了五周），他们又重新访问网站且没有使用跟踪代码或营销渠道，然后购买了商品。

用户最终的购买时间超过了 30 天，但用户却从未处于非活动状态超过 30 天。在这种情况下，您会看到收入归因于跟踪代码营销渠道，而不是归因于跟踪代码维度本身。



