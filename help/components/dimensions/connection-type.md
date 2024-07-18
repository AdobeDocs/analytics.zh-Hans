---
title: 连接类型
description: 访客如何连接到 Internet。
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 94%

---

# 连接类型

“连接类型”[维度](overview.md)显示访客如何连接到Internet。 此维度可用于确定访客如何连接到 Internet 以浏览您的网站。您可以使用它根据访客的连接速度来优化网站内容。

## 使用数据填充此维度

此维度使用[`ct`查询字符串](/help/implement/validate/query-parameters.md)和 Adobe 服务器端逻辑的组合。Adobe 使用以下规则来确定其值：

1. 如果 `ct` 查询字符串等于 `"modem"`，则将维度项设置为 `"Modem"`。AppMeasurement 仅在不受支持的 Internet Explorer 浏览器上收集这些数据，因此该维度项并不常见。
1. 检查点击的 IP 地址，并将它引用到 Adobe 内部的查找表中。如果 IP 地址来自移动运营商，则将维度项设置为 `"Mobile Carrier"`。
1. 如果 `ct` 查询字符串等于 `"lan"`，则将维度项设置为 `"LAN/Wifi"`。
1. 如果点击源自[数据源](/help/import/data-sources/overview.md)或被视为特殊类型的点击，则将维度项设置为 `"Not specified"`。
1. 如果不满足上述规则，则默认为值 `"LAN/Wifi"`。

## 维度项

维度项包括 `LAN/Wifi`、`Mobile Carrier`、`Modem` 和 `Not Specified`。

* **`LAN/Wifi`**：访客通过固网或 WiFi 热点连接到 Internet。
* **`Mobile Carrier`**：访客通过移动运营商连接到 Internet。
* **`Modem`**：访客通过不受支持的 Internet Explorer 浏览器上的调制解调器连接到 Internet。
* **`Not Specified`**：点击没有连接类型。
