---
description: 服务器端转发调用中的配置变量、HTTP 头和数据信号的综合列表及描述。
title: 服务器端转发数据和代码引用
feature: Report Suite Settings
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
role: Admin
TQID: 'https://experienceleague.adobe.com/DuHi1F4wU6EfxGe8s9EWZ54TX7KnkN3MmAOUE8a9oqw'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c354699e-6555-4397-8706-1a9a89984069
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 561
ht-degree: 88%

---

# 服务器端转发数据和代码引用

服务器端转发调用中的配置变量、HTTP 头和数据信号的综合列表及描述。

## 配置变量 {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

带有 `d_*` 前缀的参数用于标识由我们的[数据收集服务器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=zh-Hans) (DCS) 使用的系统级别特殊键值对。 另请参阅[DCS API调用支持的属性](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=zh-Hans)。

| 参数 | 描述 |
|--- |--- |
| `d_rs` | （通过基于旧版/跟踪服务器的服务器端转发进行设置）。<br>设置为将点击数据传递到 Analytics 的报表包。 |
| `d_dst_filter` | （通过基于报表包的服务器端转发进行设置）。<br>设置为将报表包 ID 传递到 Analytics 的点击。 |
| `d_dst` | 如果对 Analytics 的请求需要有关要发送回客户端的目标的内容，请设置 `d_dst=1`。<br> |
| `d_mid` | 传递到 Analytics 的 Experience Cloud ID。 |

## HTTP 头 {#section_0549705E76004F9585224AEF872066C0}

这些标头是包含数据的请求和HTTP调用中的响应等信息的字段。

| HTTP 标头 | 描述 | 由 Audience Manager 接受的 h_ 键 |
| --- | --- | --- |
| Host | 设置为在 Analytics 主机配置文件中指定的客户端的特定数据收集主机名。 它显示为 `host name .demdex.net`。 请参阅[了解 Demdex 域调用](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=zh-Hans)。 | `h_host` |
| User-Agent | 设置为传递到 Analytics 的 User-Agent 头。 | `h_user-agent` |
| Accept-Language | 设置为传递到 Analytics 的 `Accept-Language` 头。 | `h_accept-language` |
| Referer | 设置为传递到 Analytics 的页面 URL，或从传递到 Analytics 的 `Referer` 头中收集的页面 URL。 | `h_referer` |
| 反向链接 | 设置为传递到 Analytics 的页面 URL，或从传递到 Analytics 的 `Referrer` 头中收集的页面 URL。 | `h_referrer` |
| 日期 | 设置为传递到 Analytics 的 `Date` 头。 | `h_date` |

此外，`h_ip` 信号由向 DCS 发送请求的主机的 IP 生成。

## 客户定义的信号 {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

带有 `c_` 前缀的参数用于标识客户定义的变量。 另请参阅[DCS API调用支持的属性](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=zh-Hans)。

| 信号 | 描述 |
| --- |--- |
| `c_browserWidth` 和 `c_browserHeight` | 浏览器窗口宽度和高度。 |
| `c_campaign` | 由 `s.campaign` 设置。 |
| `c_channel` | 由 `s.channel` 设置。 |
| `c_clientDateTime` | 时间戳格式为 `dd/mm/yyy hh:mm:ss  W TZ`。 `TZ` 以分钟为单位，并与 `Date.getTimezoneOffset` 方法的返回值匹配。 |
| `c_colorDepth` | 指定为 16 位或 32 位颜色。 |
| `c_connectionType` | 指定连接类型。 选项包括：<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | 示例：<ul><li>AppMeasurement: `s.contextData`</li><li>[&quot;category&quot;] = &quot;news&quot;;</li><li>Signal: `c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | 指定是否可以启用Cookie。 选项包括：是、否、未知 |
| `c_currencyCode` | 用于交易的货币类型。 |
| `c_evar#` | 自定义 eVar。 |
| `c_events` | 由 `s.events` 设置。 |
| `c_hier#` | 自定义层级变量。 |
| `c_javaEnabled` | 指定是否可以启用Java。 选项包括：是、否、未知 |
| `c_javaScriptVersion` | 浏览器支持的 JavaScript 版本。 |
| `c_latitude` | 数值纬度 |
| `c_linkClick` | 选项包括：自定义、下载退出 |
| `c_linkCustomName` | 为链接提供的自定义名称（如果有）。 |
| `c_linkDownloadURL` | 下载链接 URL。 |
| `c_linkExitURL` | 退出链接 URL。 |
| `c_list#` | 自定义列表变量。 |
| `c_longitude` | 数值经度。 |
| `c_mediaPlayerType` | 用于媒体流跟踪请求。 选项包括：其他、primetime |
| `c_pageName` | 页面名称（如果已设置）。 |
| `c_pageURL` | 浏览器地址栏中的页面地址。 |
| `c_products` | 产品字符串（由 `s.products` 设置）。 |
| `c_prop` | 自定义 prop。 |
| `c_purchaseID` | 购买的唯一 ID。 |
| `c_referrer` | 当前页面之前的页面。 |
| `c_screenResolution` | 屏幕宽度和高度（以像素为单位）。 |
| `c_server` | Web 服务器名称（由 `s.server` 设置）。 |
| `c_state` | 地理区域（由 `s.state` 设置）。 |
| `c_timezone` | 时间偏移（以小时为单位）。 |
| `c_transactionID` | 交易的唯一 ID。 |
| `c_zip` | 邮政编码（由 `s.zip` 设置）。 |
