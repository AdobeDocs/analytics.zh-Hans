---
title: 连接类型
description: 访客如何连接到 Internet。
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---

# 连接类型

“连接类型”维度显示访客如何连接到Internet。 此维度有助于确定访客如何连接到Internet以浏览您的网站。 您可以使用它根据访客的连接速度优化网站内容。

## 使用数据填充此维度

此维度使用[`ct`查询字符串](/help/implement/validate/query-parameters.md)和Adobe服务器端逻辑的组合。 Adobe使用以下规则来确定其值：

1. 如果`ct`查询字符串等于`"modem"`，则将维度项目设置为`"Modem"`。 AppMeasurement仅在不支持的Internet Explorer浏览器上收集此数据，从而导致此维度项目不常见。
1. 检查点击的IP地址，并将其引用到Adobe内部的查找表。 如果IP地址来自移动设备运营商，请将维度项目设置为`"Mobile Carrier"`。
1. 如果`ct`查询字符串等于`"lan"`，则将维度项目设置为`"LAN/Wifi"`。
1. 如果点击源自[数据源](/help/import/c-data-sources/datasrc-home.md)或被视为特殊类型的点击，请将维度项目设置为`"Not specified"`。
1. 如果不满足上述任何规则，则默认值为`"LAN/Wifi"`。

## 维度项目

Dimension项目包括`LAN/Wifi`、`Mobile Carrier`、`Modem`和`Not Specified`。

* **`LAN/Wifi`**:访客通过固定电话或wifi热点连接到互联网。
* **`Mobile Carrier`**:访客通过移动运营商连接到Internet。
* **`Modem`**:访客在不支持的Internet Explorer浏览器上通过调制解调器连接到Internet。
* **`Not Specified`**:点击没有连接类型。
