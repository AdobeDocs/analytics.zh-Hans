---
title: useBeacon
description: 通过 useBeacon，您可以强制 AppMeasurement 使用浏览器 sendBeacon API
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useBeacon

大多数现代浏览器都包含本机方法 `navigator.sendBeacon()`。它通过 HTTP 将少量数据异步发送到 Web 服务器。如果启用了 `useBeacon` 变量，则 AppMeasurement 可以使用 `navigator.sendBeacon()` 方法。对于退出链接以及要在卸载页面之前发送信息的其他情况，此变量将非常有用。

如果启用了 `useBeacon`，则发送给 Adobe 的下一个点击将使用浏览器的 `navigator.sendBeacon()` 方法，而不是标准的 `GET` 图像请求。此变量同时适用于 [`s.t()`](../functions/t-method.md) 和 [`s.tl()`](../functions/tl-method.md) 图像请求。它需要 AppMeasurement 2.17.0 或更高版本。

>[!TIP] AppMeasurement 会自动为退出链接图像请求启用 `useBeacon`。

当访客使用的浏览器不支持 `useBeacon` 时，将忽略 `navigator.sendBeacon()` 变量。使用此变量需要 AppMeasurement 2.16.0 或更高版本。

## Adobe Experience Platform Launch 中的“使用信标”

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.useBeacon

`s.useBeacon` 变量是一个布尔值，用于确定 AppMeasurement 是否使用浏览器的 `navigator.sendBeacon()` 方法。其默认值为 `false`。如果要使用 `navigator.sendBeacon()` 的异步特性，请在调用跟踪函数之前将此变量设置为 `true`。

```js
s.useBeacon = true;
```

>[!NOTE] 运行跟踪调用后，此变量将被重置为 `false`。如果您多个图像的实施在同一页面加载（例如单页应用程序）中发送了请求，请在每次跟踪调用之前将此变量设置为 `true`。
