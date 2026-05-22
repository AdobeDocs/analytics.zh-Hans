---
title: useLinkTrackSessionStorage
description: 将链接跟踪数据存储在会话中，而不是 Cookie 中。
feature: Appmeasurement Implementation
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/JQc7Ii-LrL8k0KIttWFuowJCASGK2e75exSbjhG347s'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 86%

---

# useLinkTrackSessionStorage

如果您的组织使用链接跟踪，AppMeasurement 会使用 `s_sq` Cookie 来在点击之间传递信息。 某些网站配置与此 Cookie 冲突。 如果要使用浏览器会话存储，而不是 Cookie 来跟踪链接和 Activity Map 数据，则请启用此变量。

使用浏览器的会话存储来跟踪链接有若干限制：

* 会话存储在不同协议之间不起作用。 例如，您有一个通过 HTTP 协议提供的页面，而下一个页面却是通过 HTTPS 协议提供。 由于协议差异，AppMeasurement 无法访问会话存储中的链接跟踪数据。
* 会话存储无法跨子域使用。 例如，访客导航到 `store.example.com`，然后导航到 `toys.example.com`。 由于不同的子域，AppMeasurement 无法访问会话存储中的链接跟踪数据。

>[!TIP]
>
>使用会话存储进行链接跟踪的最可靠实施，是在单个子域上通过 HTTPS 协议提供所有内容。

在向 Adobe 发送点击后，AppMeasurement 会删除会话存储链接跟踪数据。 当浏览器选项卡关闭时，它也会自动过期。

## 使用Web SDK的“使用链接跟踪会话存储”

Web SDK不支持此功能。

## 通过Adobe Analytics扩展使用链接跟踪会话存储

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.useLinkTrackSessionStorage

`s.useLinkTrackSessionStorage` 变量是一个布尔值，用于确定 AppMeasurement 使用会话存储而不是 `s_sq` Cookie 来跟踪链接数据。 其默认值为 `false`。 如果希望 AppMeasurement 使用会话存储而不是 `s_sq` Cookie 来跟踪链接和 Activity Map 数据，请将此变量设置为 `true`。

```js
s.useLinkTrackSessionStorage = true;
```
