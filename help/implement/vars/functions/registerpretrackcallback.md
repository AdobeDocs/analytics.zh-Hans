---
title: registerPreTrackCallback
description: 在将点击发送到Adobe之前创建回调函数。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# registerPreTrackCallback

该变 `registerPreTrackCallback` 量允许您的组织在编译图像请求URL后但在发送之前挂接JavaScript函数。 您可以使用此变量将AppMeasurement收集的数据发送到合作伙伴或内部基础结构。

> [!IMPORTANT] 请勿调用任何跟踪函数，如变 `t` 量或 `tl` 变量 `registerPostTrackCallback` 内部。 此变量中的跟踪函数会导致图像请求无限循环！

每次调用变量 `registerPreTrackCallback` 时，您都会挂接该函数以在每次编译图像请求URL时运行。 避免在同一页面加载中多次注册同一功能。

> [!NOTE] 在和之间触发的函数的时 `registerPreTrackCallback` 间和 `registerPostTrackCallback` 顺序不保证。 避免这两个函数之间的依赖关系。

## 在Adobe Experience Platform Launch中注册预跟踪回调

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.registerPreTrackCallback和启动自定义代码编辑器

它 `s.registerPreTrackCallback` 是将函数作为其唯一参数的函数。 嵌套函数在发送图像请求之前即运行。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

如果要在代码中使用图像请求URL，请引用嵌套函 `requestUrl` 数中的字符串参数。 您可以解析变 `requestUrl` 量以供您使用；调整此变量不会影响数据收集。

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

函数中可以包含其他参 `s.registerPreTrackCallback` 数，该参数可用于嵌套函数：

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

> [!NOTE] 在此函数中设置页面变 `requestUrl` 量或更改字符串不 *会影响* 在此函数调用后不久发送的图像请求。
