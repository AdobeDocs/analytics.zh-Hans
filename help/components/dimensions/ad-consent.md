---
title: 广告平台同意书
description: 请参阅第三方广告提供商的广告同意配置。
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# 广告平台同意书

“广告平台同意”维度[维度](overview.md)显示是否收集了同意数据，以便将数据发送到Google、Meta等第三方广告提供商。

目前，此维度仅用于Google。 由于欧洲隐私法规、《数字市场法》(DMA)的要求，Google要求发送到其服务器并在欧洲收集的数据必须表明是否征得同意。 某些Analytics客户会通过Adobe Advertising将事件数据作为转化事件发送到Google。

将来，此维度可用于支持对其他第三方广告提供商的其他同意信息的编码。

## 使用数据填充此维度

此维度从以下[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)收集数据

* `contextData.['adConsent']`

您可以使用Google同意字段的相关值填充上下文数据变量

* `ad_user_data` （第1个字符）和
* `ad_personalization` （第2个字符）。

有关详细信息，请参阅Google Ads API参考中的[同意](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent)。

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

* 数据馈送：广告同意数据可使用`dataprivacydmaconsent` [列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)获得。
* Data Warehouse报告：广告同意数据可使用&#x200B;**[!UICONTROL 广告平台同意]**&#x200B;维度获得。

贵组织确定实施此上下文数据变量的逻辑。 该值不会在设置的点击之外继续存在，因此您必须在每个页面上设置上下文数据变量。

当您通过Adobe Advertising将广告数据作为转化事件发送到GoogleAdobe Advertising时，请咨询Adobe Analytics团队以协助进行集成。

有关详细信息，请参阅[隐私报表](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md)。
