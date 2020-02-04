---
title: useBeacon
description: 通过 useBeacon，您可以强制 AppMeasurement 使用浏览器 sendBeacon API
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# useBeacon

大多数现代浏览器都包含本机方法 `navigator.sendBeacon()`。 它通过HTTP将少量数据异步发送到Web服务器。 如果启用了变 `navigator.sendBeacon()` 量，AppMeasurement可 `useBeacon` 以使用该方法。 对于退出链接以及您希望在卸载页面之前发送信息的其他情况，此功能非常有用。

如果 `useBeacon` 启用此功能，则发送到Adobe的下一次点击将使用浏览器的方 `navigator.sendBeacon()` 法而不是标准图 `GET` 像请求。 此变量同时适用于 `s.t()` 和 `s.tl()` 图像请求。它需要AppMeasurement 2.17.0或更高版本。

> [!TIP] AppMeasurement可自动启 `useBeacon` 用退出链接图像请求。

当访 `useBeacon` 客使用不支持的浏览器时，该变量将被忽略 `navigator.sendBeacon()`。

## 在Adobe Experience Platform Launch中使用信标

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和启动自定义代码编辑器中的s.useBeacon

该 `s.useBeacon` 变量是一个布尔值，它确定AppMeasurement是否使用浏览器的方 `navigator.sendBeacon()` 法。 Its default value is `false`. 如果要使用的 `true` 异步性质，请在调用跟踪函数之前将此变量设置为 `navigator.sendBeacon()`。

```js
s.useBeacon = true;
```

> [!NOTE] 运行跟踪调用后，此变量将重置为 `false`。 如果您的实施在同一页面加载（如单页应用程序）中发送多个图像请求，请将此变量设置为每次跟踪调 `true` 用之前的值。
