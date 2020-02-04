---
title: registerPostTrackCallback
description: 在向Adobe发送点击后创建回调函数。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# registerPostTrackCallback

该 `registerPostTrackCallback` 变量允许您的组织在成功将点击发送到Adobe后立即挂接JavaScript函数。 如果跟踪调用失败，则此函数不运行。 您可以使用此变量将AppMeasurement收集的数据发送到合作伙伴或内部基础结构，或清除单页应用程序中的变量值。

> [!IMPORTANT] 请勿调用任何跟踪函数，如变 `t` 量或 `tl` 变量 `registerPostTrackCallback` 内部。 此变量中的跟踪函数会导致图像请求无限循环！

每次调用变量 `registerPostTrackCallback` 时，您都会挂接该函数以在成功发送图像请求后立即运行。 避免在同一页面加载中多次注册同一功能。

> [!NOTE] 在和之间触发的函数的时 `registerPostTrackCallback` 间和 `registerPostTrackCallback` 顺序不保证。 避免这两个函数之间的依赖关系。

## 在Adobe Experience Platform Launch中注册帖子跟踪回调

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.registerPostTrackCallback和启动自定义代码编辑器

它 `s.registerPostTrackCallback` 是将函数作为其唯一参数的函数。 嵌套函数在发送图像请求之前即运行。

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

如果要在代码中使用图像请求URL，请引用嵌套函 `requestUrl` 数中的字符串参数。 您可以解析变 `requestUrl` 量以供您使用；调整此变量不会影响数据收集。

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

函数中可以包含其他参 `s.registerPostTrackCallback` 数，该参数可用于嵌套函数：

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## 用例示例

在后跟 `clearVars()` 踪回调中注册该函数对单页应用程序很有帮助。 每次您成功将点击发送到Adobe时，该函 `clearVars()` 数都会运行。 然后，您的实现可以再次定义变量，而不必担心值的持久性不正确。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
