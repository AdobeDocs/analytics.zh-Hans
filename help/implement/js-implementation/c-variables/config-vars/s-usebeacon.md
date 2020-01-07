---
title: useBeacon
description: 通过 useBeacon，您可以强制 AppMeasurement 使用浏览器 sendBeacon API
keywords: Analytics Implementation
translation-type: ht
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

`s.useBeacon` 变量会强制下一个请求使用浏览器的 [sendBeacon API](https://developer.mozilla.org/zh-CN/docs/Web/API/Navigator/sendBeacon)。通过使用 `s.sendBeacon`，可在页面上下文外部发送 HTTP 请求。对于退出链接以及要在卸载页面之前发送信息的其他情况，此变量将非常有用。

只能为 AppMeasurement 触发的下一个请求设置此值。请求触发后，`s.useBeacon` 将重置为 false。此变量同时适用于 `s.t()` 和 `s.tl()` 图像请求。

若要使用 `s.useBeacon` 变量，则需要 AppMeasurement 2.17.0 或更高版本。

> [!NOTE] [退出链接](s-linktrackvars.md)可自动使用此变量，而无需额外使用任何其他配置。

## 语法

```js
s.useBeacon = true;
```
