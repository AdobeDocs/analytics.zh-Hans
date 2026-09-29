---
title: 连接类型
description: 访客如何连接到 Internet。
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: 'https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs'
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
source-wordcount: '286'
ht-degree: 76%
---
# 连接类型

“连接类型”[维度](overview.md)显示访客如何连接到Internet。 此维度可用于确定访客如何连接到 Internet 以浏览您的网站。 您可以使用它根据访客的连接速度来优化网站内容。

## 使用数据填充此维度

此维度由收集的数据和Adobe服务器端逻辑的组合决定，而不是由您设置的变量决定。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无 |
| **Web SDK / XDM字段** | 无 |
| **查询参数** | [`ct`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<connectionType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

Adobe 使用以下规则来确定其值：

1. 如果 `ct` 查询字符串等于 `"modem"`，则将维度项设置为 `"Modem"`。 AppMeasurement 仅在不受支持的 Internet Explorer 浏览器上收集这些数据，因此该维度项并不常见。
1. 检查点击的 IP 地址，并将其与 Adobe 内部的查找表进行比对。 如果 IP 地址来自移动运营商，则将维度项设置为 `"Mobile Carrier"`。
1. 如果 `ct` 查询字符串等于 `"lan"`，则将维度项设置为 `"LAN/Wifi"`。
1. 如果点击源自[数据源](/help/import/data-sources/overview.md)或被视为特殊类型的点击，则将维度项设置为 `"Not specified"`。
1. 如果不满足上述规则，则默认为值 `"LAN/Wifi"`。

## 维度项目

维度项包括 `LAN/Wifi`、`Mobile Carrier`、`Modem` 和 `Not Specified`。

* **`LAN/Wifi`**：访客通过固网或 WiFi 热点连接到 Internet。
* **`Mobile Carrier`**：访客通过移动运营商连接到 Internet。
* **`Modem`**：访客通过不受支持的 Internet Explorer 浏览器上的调制解调器连接到 Internet。
* **`Not Specified`**：点击没有连接类型。
