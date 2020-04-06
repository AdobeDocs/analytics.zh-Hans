---
title: useLinkTrackSessionStorage
description: 将链接跟踪数据存储在会话存储中，而不是Cookie中。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useLinkTrackSessionStorage

如果您的组织使用链接跟踪，则AppMeasurement使用 `s_sq` cookie在点击之间传递信息。 某些网站配置与此Cookie相冲突。 如果要使用浏览器会话存储来跟踪链接和活动映射数据而不是cookie，请启用此变量。

使用浏览器的会话存储跟踪链接有若干限制：

* 会话存储在协议之间不起作用。 例如，您有一个通过HTTP服务的页面，而下一个通过HTTPS服务的页面。 AppMeasurement无法访问会话存储中的链接跟踪数据，因为协议差异。
* 会话存储不能跨子域工作。 例如，访客导航到， `store.example.com`然后导航到 `toys.example.com`。 AppMeasurement由于不同的子域，无法访问会话存储中的链接跟踪数据。

>[!TIP] 使用用于链接跟踪的会话存储的最可靠的实现通过一个子域通过HTTPS提供所有内容。

AppMeasurement在向Adobe发送点击后删除会话存储链接跟踪数据。 浏览器选项卡关闭后，它也会自动过期。

## 在Adobe Experience Platform Launch中使用链接跟踪会话存储

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## s.useLinkTrackSessionStorage in AppMeasurement and Launch自定义代码编辑器

该变 `s.useLinkTrackSessionStorage` 量是一个布尔值，它确定AppMeasurement是否使用会话存储来跟踪链接数据而不是 `s_sq` cookie。 其默认值为 `false`。如果希望AppMeasurement `true` 使用会话存储而不是 `s_sq` cookie来跟踪链接和活动映射，请将此变量设置为。

```js
s.useLinkTrackSessionStorage = true;
```
