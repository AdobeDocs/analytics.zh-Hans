---
title: useBeacon
description: useBeacon允许您强制AppMeasurement使用浏览器sendBeacon API
keywords: Analytics 实施
seo-description: useBeacon允许您强制AppMeasurement使用浏览器sendBeacon API
translation-type: tm+mt
source-git-commit: f89d909e539cee2b78798c165fcb405773418056

---


# s.useBeacon

该 `s.useBeacon` 变量强制下一个请求使用浏览器的 [sendBeacon API](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)。 使用 `s.sendBeacon` 允许在页面上下文之外发送HTTP请求。 对于退出链接以及要在卸载页面之前发送信息的其他情况，此功能非常有用。

设置此值仅适用于AppMeasurement触发的下一个请求。 请求触发后，重置 `s.useBeacon` 为false。 此变量同时适用于 `s.t()` 图像 `s.tl()` 请求。

使用该 `s.useBeacon` 变量需要AppMeasurement 2.17.0或更高版本。

> [!NOTE] ExitLinks [自动使用此变量](s-linktrackvars.md) ，无需任何其他配置。

## 语法

```js
s.useBeacon = true;
```
