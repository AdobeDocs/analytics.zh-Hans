---
title: registerPreTrackCallback
description: 在将点击发送到 Adobe 之前创建回调函数。
feature: Appmeasurement Implementation
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 55%

---

# registerPreTrackCallback

`registerPreTrackCallback` 变量允许贵组织在编译图像请求 URL 后但在将其发送之前挂接 JavaScript 函数。您可以使用此变量将 AppMeasurement 收集的数据发送到合作伙伴或内部基础结构。

>[!WARNING]
>
>请勿在`registerPreTrackCallback`变量内进行任何跟踪调用，如[`t()`](t-method.md)或[`tl()`](tl-method.md)。 在此变量中设置跟踪调用会导致图像请求无限循环！

每次调用 `registerPreTrackCallback` 变量时，您都会挂接该函数以在每次编译图像请求 URL 时运行。避免在同一页面加载过程中多次注册同一函数。

>[!NOTE]
>
>`registerPreTrackCallback` 和 `registerPostTrackCallback` 之间触发函数的时间和顺序无法得到保证。避免这两个函数之间存在依赖关系。

## 使用Web SDK扩展预跟踪回调

Web SDK无法在编译数据后但在将数据发送到Adobe之前挂接函数。 但是，您可以使用`onBeforeEventSend`注册一个函数，以便在发送数据之前执行。

1. 使用您的AdobeID凭据登录到[Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) UI。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL Adobe Experience Platform Web SDK]下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 在[!UICONTROL 数据收集]下，单击&#x200B;**[!UICONTROL 在事件发送回调代码之前编辑]**&#x200B;按钮。
1. 将所需的代码置于编辑器中。

## 手动实施Web SDK的预跟踪回调

Web SDK无法在编译数据后但在将数据发送到Adobe之前挂接函数。 但是，您可以使用`onBeforeEventSend`注册一个函数，以便在发送数据之前执行，类似于`doPlugins`。 有关详细信息，请参阅Web SDK文档中的[全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## 使用Adobe Analytics扩展预跟踪回调

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.registerPreTrackCallback

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

您可以在 `s.registerPreTrackCallback` 函数中包含其他参数，这些参数可在嵌套函数中使用：

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>设置页面变量或更改此函数中的 `requestUrl` 字符串&#x200B;**不会**&#x200B;影响在此函数调用后不久发送的图像请求。请改用 [`doPlugins()`](doplugins.md) 变量。
