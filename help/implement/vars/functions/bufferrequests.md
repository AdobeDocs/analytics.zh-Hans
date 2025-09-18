---
title: bufferRequests
description: 增强捕获立即卸载页面的浏览器的链接跟踪请求的可靠性。
feature: Appmeasurement Implementation
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 325c035c0b5a9cc828be22ef7781d3b67f104476
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# bufferRequests

`bufferRequests()`方法允许您在当前页面上缓存图像请求，而不是将其发送到Adobe。 在浏览器不支持[`navigator.sendBeacon()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Navigator/sendBeacon)或卸载页面时取消图像请求的情况下，触发此方法很有用。 WebKit浏览器的许多版本（如Safari）通常都会在单击链接时显示停止图像请求的行为。 `bufferRequests()`方法适用于AppMeasurement v2.25.0或更高版本的所有版本。

当您在同一浏览器会话的后续页面上调用[`t()`](t-method.md)或[`tl()`](tl-method.md)时，如果尚未在该页面上调用`bufferRequests()`，则除了该页面的图像请求之外，还将发送所有缓冲请求。 缓冲的请求以正确的顺序发送，即当前页面的图像请求在最后发送。

>[!TIP]
>
>与发送数据的页面共享缓冲请求的时间戳。 如果您希望提高在准确时间内记录缓冲请求的精度，则可以在缓冲请求之前设置[`timestamp`](../page-vars/timestamp.md)页面变量。 如果使用此变量，请确保启用[可选时间戳](/help/admin/tools/manage-rs/edit-settings/general/timestamp-configuration.md) — 如果未启用，则所有带有时间戳的点击将永久丢失！

## 限制

调用`bufferRequests()`方法时，请记住以下限制。 由于此方法使用[`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)，因此适用许多相同的限制：

* 目标链接必须驻留在同一域和子域上。 即使两个域或子域具有相同的Adobe Analytics实施，缓冲的请求也不能跨这些域或子域工作。 此限制还意味着您无法使用缓冲请求跟踪退出链接。
* 目标链接必须使用与当前页面相同的协议。 您不能在HTTP和HTTPS之间发送缓冲请求。
* 缓冲的请求会一直存储到您调用`t()`或`tl()`而未先调用`bufferRequests()`为止，或者直到关闭浏览器或选项卡为止。 如果浏览器会话在将数据发送到Adobe之前结束，则未发送的缓冲请求将永久丢失。
* 如果浏览器不支持[Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)或[JSON API](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)，则会向浏览器控制台输出警告，AppMeasurement将尝试使用`t()`方法立即发送图像请求。

## Web SDK中的缓冲请求

Web SDK当前不提供缓冲请求的功能。

## 使用Adobe Analytics扩展程序的缓冲请求

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.bufferRequests()

在调用`bufferRequests()`或`t()`之前调用`tl()`方法。 调用`bufferRequests()`时，后续跟踪调用将写入会话存储中，而不是发送到Adobe数据收集服务器。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```
