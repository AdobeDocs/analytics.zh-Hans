---
title: 广告平台同意书
description: 请参阅第三方广告提供商的广告同意配置。
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: 'https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 5%
---
# 广告平台同意书

“广告平台同意”维度[维度](overview.md)显示是否收集了同意数据，以便将数据发送到Google、Meta等第三方广告提供商。

目前，此维度仅用于Google。 由于欧洲隐私法规、《数字市场法》(DMA)的要求，Google要求发送到其服务器并在欧洲收集的数据必须表明是否征得同意。 某些Analytics客户会通过Adobe Advertising将事件数据作为转化事件发送到Google。

将来，此维度可用于支持对其他第三方广告提供商的其他同意信息的编码。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `contextData.['adConsent']`收集数据。 您使用相关的Google同意字段值填充此变量： `ad_user_data` （第一个字符）和`ad_personalization` （第二个字符）。 有关详细信息，请参阅Google Ads API参考中的[同意](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent)。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（通过`adConsent`上下文数据变量设置） |
| **Web SDK / XDM字段** | 无 |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

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

当您通过Adobe Advertising将广告数据作为转化事件发送到Google时，请咨询Adobe Analytics团队以协助进行集成。

有关详细信息，请参阅[隐私报表](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md)。
