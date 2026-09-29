---
title: 反向链接域
description: 访客在点击进入到您的网站之前所处的首要域。
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: 'https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
source-wordcount: '458'
ht-degree: 81%
---
# 反向链接域

“反向链接域”[维度](overview.md)报告访客点击了哪些域才能访问您的网站。 此维度有助于了解哪些第三方网站给您的网站带来了最多的流量。 链接必须存在于外部网站上，且访客必须单击该链接才能显示维度项目。

>[!IMPORTANT]
>
>必须配置报表包的[内部 URL 过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)，才能使用此维度。 无法配置内部 URL 过滤器，可能会包含内部域或阻止出现外部域。

同一报表在 Analysis Workspace 和 Data Warehouse 中可能会显示不同的结果。 Analysis Workspace 会报告每个页面的反向链接域，但不包括与内部 URL 过滤器匹配的值。 Data Warehouse 则仅报告访问的第一个反向链接域，并且会忽略内部 URL 过滤器。

## 使用数据填充此维度

Adobe使用反向链接URL的域部分，从每次点击的[反向链接](referrer.md)派生此维度。 没有要设置的变量。 必须配置报表包的[内部URL过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)；否则，可能会包含内部域或阻止出现外部域。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自反向链接） |
| **Web SDK / XDM字段** | 无（派生自反向链接） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 访问 |

Adobe 会在一次访问期间保留反向链接域。 如果访客离开并在单次访问中点击不同域上的链接，则新值会更新并且在剩余的访问时间内持续存在。 如果只想查看原始值，请参阅[原始反向链接域](original-referring-domain.md)。

## 维度项目

维度项目包括访客点击进入您的网站的域。 如果点击没有任何反向链接数据（设置或保留），则它会分组到维度项目 `"Typed/Bookmarked"` 下。 此维度项目表示不存在反向链接值，例如，如果访客在地址栏中手动键入浏览器地址，或单击书签。 对于不适用于 Analytics 的重定向，也会显示 `"Typed/Bookmarked"` 维度项目。 请参阅技术说明用户指南中的[重定向和别名](/help/technotes/redirects.md)。

### 包含 `googleusercontent.com` 的维度项目

用户可以查看包含域 `googleusercontent.com` 的维度项目。

* **缓存的页面**：Google Spider 会不断地抓取网页并存储页面副本，以防它们离线。 在大多数搜索结果旁边，通过单击“已缓存”链接，即可使用这些缓存的页面。 当用户单击此链接并查看 Google 缓存的内容时，`googleusercontent.com` 是维度项目。
* **翻译页面**：Google 提供了一项强大而便捷的翻译服务。 使用此服务查看站点时，服务源自 `googleusercontent.com`。 如果用户单击某个链接以返回到原始内容，则会显示此维度项目。
