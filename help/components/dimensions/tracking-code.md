---
title: 跟踪代码
description: 跟踪代码或营销活动的名称。
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
TQID: 'https://experienceleague.adobe.com/8e9126PxGCNXJqo4a3XYTgXwrcHdf34FVwygpHXm5JI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 88%
---
# 跟踪代码

“跟踪代码”[维度](overview.md)会列出您的网站上跟踪代码的名称。 您可以将具有不同查询字符串参数值的链接放在互联网的不同位置。 此维度可以帮助您了解哪些链接最能成功为您的网站带来流量。

在电子邮件、广告、社交媒体帖子以及您组织使用的其他营销活动中附加跟踪代码查询字符串很常见。

## 使用数据填充此维度

AppMeasurement 使用 [`campaign`](/help/implement/vars/page-vars/campaign.md) 变量收集此数据。 此变量通常使用[`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md)实用工具方法从查询字符串获取其值，但您的组织会确切确定如何设置它。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`campaign`](/help/implement/vars/page-vars/campaign.md) |
| **Web SDK / XDM字段** | [`marketing.trackingCode`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/event/campaign-marketing-details) |
| **查询参数** | [`v0`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<campaign>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 255字节 |
| **持久性** | 可配置 |

## 维度项目

维度项目包括您的网站上的跟踪代码的名称。 贵组织会确定您要使用的具体维度项目。 更多信息请参阅[营销活动跟踪](/help/implement/use-cases/campaign-tracking.md)。

## 比较跟踪代码维度与收集跟踪代码的营销渠道

一些设置营销渠道处理规则的用户会配置一项规则，该规则采用跟踪代码维度中使用的所有值。 尽管这是一种不错的做法，但由于固有的处理和架构差异，它们彼此不同。 以下列表说明了为何这两种方法看上去很相似，却可以改变归因行为。

### 处理规则中的优先渠道

在列表中排在前面的营销渠道处理规则可以阻止点击被归因于“跟踪代码”营销渠道。 例如：

1. 您将“社交网络”设置为第一条规则，并将“跟踪代码”设置为第二条规则。
2. 假设用户在社交媒体网站上发布了一个指向您的网站的链接，其中包含跟踪代码，然后用户的几个朋友点击了指向您的网站的链接。

那么由于“社交网络”是第一个营销渠道处理规则，因此这些用户将归因于“社交网络”营销渠道，而不是“跟踪代码”营销渠道。

### 其他营销渠道可通过最近联系获得归因

处理标准的跟踪代码维度时，您无需担心网站的其他部分会盗用归因。 但是，在营销渠道中，用户可能会匹配到其他规则，从而产生不同的归因。 例如：

1. 您将“跟踪代码”设置为第一个渠道，并将“直接”设置为第二个渠道。
2. 用户最初通过跟踪代码到达您的网站，但随后离开。
3. 第二天，他们将您网站的 URL 键入地址栏，然后购买了商品。

在这个例子中，“跟踪代码”营销渠道不会获得该购买的最近联系点数。 相反，点数会计入“直接”营销渠道。


### 有效期限差异

营销渠道具有连续 30 天的访客参与有效期限，无论是否接触了渠道。 而跟踪代码的有效期限则取决于变量的设置时间。 例如：

1. 您的访客参与到期期限为 30 天，并且还将“跟踪代码”维度配置为在 30 天之后到期。
2. 用户通过跟踪代码到达您的网站。 他们浏览网站，然后离开。
3. 三周后，他们再次访问网站时没有跟踪代码或营销渠道，然后再次离开。
4. 又过了两周后（自最初访问经过了五周），他们又重新访问网站且没有使用跟踪代码或营销渠道，然后购买了商品。

用户最终的购买时间超过了 30 天，但用户却从未处于非活动状态超过 30 天。 在这种情况下，您会看到收入归因于跟踪代码营销渠道，而不是归因于跟踪代码维度本身。



