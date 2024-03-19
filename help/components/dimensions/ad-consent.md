---
title: 广告同意
description: 请参阅第三方广告提供商的广告同意配置。
feature: Dimensions
source-git-commit: b5aba8a42f524ef3367a779e6fb1a731de680750
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 3%

---

# 广告同意

“广告同意” [维度](overview.md) 显示是否同意向第三方广告提供商(如Google、Meta等)发送数据。

目前，此维度仅用于Google。 由于欧洲隐私法规、《数字市场法》(DMA)的要求，Google要求发送到其服务器并在欧洲收集的数据必须表明是否征得同意。 某些Analytics客户会通过Adobe Advertising将事件数据作为转化事件发送到Google。

将来，此维度可用于支持对其他第三方广告提供商的附加同意信息进行编码。

## 使用数据填充此维度

此维度从以下来源收集数据 [上下文数据变量](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`

您可以使用Google同意字段的相关值填充上下文数据变量

* `ad_user_data` （第一个字符）和
* `ad_personalization` （第2个字符）。

请参阅 [Google Ads API参考中的同意](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) 以了解更多信息。

每个字段的可能值可以是：

| 值 | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | 同意使用Google获取广告用户数据。 | 同意使用Google进行广告个性化。 |
| `N` | 拒绝同意使用广告用户数据的Google。 | 拒绝同意使用Google进行广告个性化。 |
| `U` | 未指定。 | 未指定。 |

以下示例授予对Google的广告用户数据的同意，但不授予对广告个性化的同意：

```
contextData.['adConsent'] = "YN..."
```

当前会忽略第一个和第二个字符以外的字符。

## 使用数据

您可以使用收集的广告同意数据：

* 数据馈送：广告同意数据可通过以下方式获取： `dataprivacydmaconsent` [列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Data Warehouse报表：广告同意数据可通过以下方式获取： **[!UICONTROL 广告平台同意]** 维度。


贵组织确定实施此上下文数据变量的逻辑。 该值不会在设置的点击之外继续存在，因此您必须在每个页面上设置上下文数据变量。

Adobe Analytics当您通过Adobe Advertising将广告数据作为转化事件发送到Google时，请咨询Adobe Advertising团队以协助进行集成。

有关详细信息，请参阅， [隐私报表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md).
