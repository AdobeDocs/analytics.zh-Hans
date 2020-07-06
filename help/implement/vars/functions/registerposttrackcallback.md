---
title: registerPostTrackCallback
description: 在向 Adobe 发送点击后创建回调函数。
translation-type: tm+mt
source-git-commit: 0d7e7dcb2cc382d83e267e51b1abeff38da270d3
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 95%

---


# registerPostTrackCallback

`registerPostTrackCallback` 变量允许贵组织在成功将点击发送到 Adobe 后立即挂接 JavaScript 函数。如果跟踪调用失败，则此函数不会运行。您可以使用此变量将 AppMeasurement 收集的数据发送到合作伙伴或内部基础结构，或者清除单页应用程序中的变量值。

>[!IMPORTANT] 在 `registerPostTrackCallback` 变量内请勿调用任何跟踪函数，如 [`t()`](t-method.md) 或 [`tl()`](tl-method.md)。此变量中的跟踪函数可能会导致图像请求无限循环！

每次调用 `registerPostTrackCallback` 变量时，您都会挂接该函数以使其在成功发送图像请求后立即运行。避免在同一页面加载过程中多次注册同一函数。

>[!NOTE] [`registerPreTrackCallback`](registerpretrackcallback.md) 和 `registerPostTrackCallback` 之间触发函数的时间和顺序无法得到保证。避免这两个函数之间存在依赖关系。

## 在 Adobe Experience Platform Launch 中注册后跟踪回调

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.registerPostTrackCallback

`s.registerPostTrackCallback` 是一个函数，只接受函数作为参数。嵌套函数在成功发送图像请求后立即运行。

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

## 用例示例

在后跟踪回调中注册该 [`clearVars()`](clearvars.md) 函数对单页应用程序可能很有益处。每次您将点击成功发送到 Adobe 时，`clearVars()` 函数都会运行。然后，您的实施可以再次定义变量，而不必担心会错误地保留值。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
