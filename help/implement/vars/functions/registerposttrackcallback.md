---
title: registerPostTrackCallback
description: 在向 Adobe 发送点击后创建回调函数。
feature: Appmeasurement Implementation
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 73%

---

# registerPostTrackCallback

`registerPostTrackCallback` 变量允许贵组织在成功将点击发送到 Adobe 后立即挂接 JavaScript 函数。如果跟踪调用失败，则此函数不会运行。您可以使用此变量将 AppMeasurement 收集的数据发送到合作伙伴或内部基础结构，或者清除单页应用程序中的变量值。

>[!WARNING]
>
>请勿在`registerPostTrackCallback`变量内进行任何跟踪调用，如[`t()`](t-method.md)或[`tl()`](tl-method.md)。 在此变量中设置跟踪调用会导致图像请求无限循环！

每次调用 `registerPostTrackCallback` 变量时，您都会挂接该函数以使其在成功发送图像请求后立即运行。避免在同一页面加载过程中多次注册同一函数。

>[!NOTE]
>
>[`registerPreTrackCallback`](registerpretrackcallback.md) 和 `registerPostTrackCallback` 之间触发函数的时间和顺序无法得到保证。避免这两个函数之间存在依赖关系。

## 使用Web SDK扩展的后跟踪回调

即将推出！

## 手动实施Web SDK的后跟踪回调

成功将数据发送到JavaScript后，在发送事件以注册函数时，您可以使用Adobe Promise。

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

有关详细信息，请参阅Web SDK文档中的[处理来自事件的响应](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hans#handling-responses-from-events)。

## 使用Adobe Analytics扩展注册后跟踪回调

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.registerPostTrackCallback

`s.registerPostTrackCallback` 是一个函数，只接受函数作为参数。嵌套函数在成功发送图像请求之后立即运行。

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

如果要在代码中使用图像请求 URL，请引用嵌套函数中的 `requestUrl` 字符串参数。您可以解析 `requestUrl` 变量以满足您的所需用途；调整此变量不会影响数据收集。

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

`s.registerPostTrackCallback` 函数中可以包含其他参数，该参数可用于嵌套函数：

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## 用例

在后跟踪回调中注册该 [`clearVars()`](clearvars.md) 函数对单页应用程序可能很有益处。每次您将点击成功发送到 Adobe 时，`clearVars()` 函数都会运行。然后，您的实施可以再次定义变量，而不必担心会错误地保留值。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
