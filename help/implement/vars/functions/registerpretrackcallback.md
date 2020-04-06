---
title: registerPreTrackCallback
description: 在将点击发送到 Adobe 之前创建回调函数。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# registerPreTrackCallback

`registerPreTrackCallback` 变量允许贵组织在编译图像请求 URL 后但在将其发送之前挂接 JavaScript 函数。您可以使用此变量将 AppMeasurement 收集的数据发送到合作伙伴或内部基础结构。

>[!IMPORTANT] 请勿调用任何跟踪调用，如变 [`t()`](t-method.md) 量 [`tl()`](tl-method.md) 或变量 [`registerPostTrackCallback`](registerposttrackcallback.md) 内。 此变量中的跟踪函数可能会导致图像请求无限循环！

每次调用 `registerPreTrackCallback` 变量时，您都会挂接该函数以在每次编译图像请求 URL 时运行。避免在同一页面加载过程中多次注册同一函数。

>[!NOTE] `registerPreTrackCallback` 和 `registerPostTrackCallback` 之间触发函数的时间和顺序无法得到保证。避免这两个函数之间存在依赖关系。

## 在 Adobe Experience Platform Launch 中注册预跟踪回调

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.registerPreTrackCallback

`s.registerPreTrackCallback` 是一个函数，只接受函数作为参数。嵌套函数在发送图像请求之前运行。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

如果要在代码中使用图像请求 URL，请引用嵌套函数中的 `requestUrl` 字符串参数。您可以解析 `requestUrl` 变量以满足您的所需用途；调整此变量不会影响数据收集。

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

您可以在函数中包含其 `s.registerPreTrackCallback` 他参数，该参数可在嵌套函数中使用：

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE] 在此函数中设置页面变量或更改 `requestUrl` 字符串&#x200B;**不**&#x200B;会影响在此函数调用后不久发送的图像请求。请改用 [`doPlugins()`](doplugins.md) 变量。
