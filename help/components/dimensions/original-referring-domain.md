---
title: 原始反向链接域
description: 访客在点击进入您的网站之前所处的首个反向链接域。
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: 'https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU'
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 72%
---
# 原始反向链接域

“原始反向链接域”[维度](overview.md)报告访客点击进入您的网站的第一个反向链接域。 设置后，它在该访客 ID 的整个存留期内包含相同的值。 此维度有助于了解哪些第三方网站最初为您的网站带来了流量。

>[!IMPORTANT]
>
>必须配置报表包的[内部 URL 过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)，才能使用此维度。 无法配置内部 URL 过滤器，可能会包含内部域或阻止出现外部域。

## 使用数据填充此维度

Adobe使用该反向链接URL的域部分从访客的前[个反向链接](referrer.md)派生此维度。 没有要设置的变量。 必须配置报表包的[内部URL过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)；否则，可能会包含内部域或阻止出现外部域。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自访客的第一个反向链接） |
| **Web SDK / XDM字段** | 无（派生自访客的第一个反向链接） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 访客 |

如果访客随时离开并点击不同域上的链接，则不会记录新值。 要查看新值，请参阅[反向链接域](referring-domain.md)。

## 维度项目

维度项目包括访客点击进入您的网站的域。 如果点击没有任何反向链接数据（设置或保留），则它会分组到维度项目 `"None"` 下。 此维度项目表示不存在反向链接值，例如，如果访客在地址栏中手动键入浏览器地址，或单击书签。

## 比较反向链接域与原始反向链接域

在不同访问之间，反向链接域可能会发生改变。 例如，访客通过 `google.com` 到达您的网站，一周后，又通过 `twitter.com` 到达您的网站。 最终，他们在您的网站上进行购买。 如果将“反向链接域”用作维度并采用最近联系归因，则 `twitter.com` 会获得该购买的点数。 如果将“原始反向链接域”用作维度，则无论采用何种归因模型，`google.com` 都会获得该购买的点数。

在给定访客 ID 的整个存留期内，原始反向链接域从不会发生改变。
