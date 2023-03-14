---
title: useBeacon
description: 通过 useBeacon，您可以强制 AppMeasurement 使用浏览器 sendBeacon API
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 61%

---

# useBeacon

大多数现代浏览器都包含本机方法 `navigator.sendBeacon()`。它通过 HTTP 将少量数据异步发送到 Web 服务器。如果启用了 `useBeacon` 变量，则 AppMeasurement 可以使用 `navigator.sendBeacon()` 方法。对于退出链接以及要在卸载页面之前发送信息的其他情况，此变量将非常有用。

如果启用了 `useBeacon`，则发送给 Adobe 的下一个点击将使用浏览器的 `navigator.sendBeacon()` 方法，而不是标准的 `GET` 图像请求。此变量同时适用于 [`s.t()`](../functions/t-method.md) 和 [`s.tl()`](../functions/tl-method.md) 图像请求。它需要 AppMeasurement 2.17.0 或更高版本。

>[!TIP]
>
> AppMeasurement 会自动为退出链接图像请求启用 `useBeacon`。

当访客使用的浏览器不支持 `useBeacon` 时，将忽略 `navigator.sendBeacon()` 变量。使用此变量需要 AppMeasurement 2.16.0 或更高版本。

## 通过Web SDK扩展使用sendBeacon API

此 **[!UICONTROL 文档将卸载]** Action Configuration中的复选框可确定发送到Adobe的数据是否使用sendBeacon API。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection?lang=zh-Hans)。
1. 单击所需的标记属性。
1. 转到 [!UICONTROL 规则] 选项卡，然后单击所需的规则。
1. 下 [!UICONTROL 操作]，单击所需的操作或单击 **&#39;+&#39;** 图标以添加新操作。
1. 将“Extension（扩展）”下拉列表设置为 **[!UICONTROL Adobe Experience Platform Web SDK]** 和 [!UICONTROL 操作类型] 到 **[!UICONTROL 发送事件]**
1. 单击复选框 **[!UICONTROL 文档将卸载]** 在右边。

如果选中此框，则会使用sendBeacon API将数据发送到Adobe。 默认情况下，该复选框处于未选中状态。

## 使用sendBeacon API手动实施Web SDK

设置 `documentUnloading` 到 `true` 发送事件时。 如果未设置，则其默认值为 `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

参见 [使用sendBeacon API](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) 有关更多信息，请参阅Web SDK文档。

## 使用Adobe Analytics扩展的“使用信标”

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.useBeacon

`s.useBeacon` 变量是一个布尔值，用于确定 AppMeasurement 是否使用浏览器的 `navigator.sendBeacon()` 方法。其默认值为 `false`。如果要使用 `navigator.sendBeacon()` 的异步特性，请在调用跟踪函数之前将此变量设置为 `true`。

```js
s.useBeacon = true;
```

>[!NOTE]
>
>运行跟踪调用后，此变量将被重置为 `false`。如果您多个图像的实施在同一页面加载（例如单页应用程序）中发送了请求，请在每次跟踪调用之前将此变量设置为 `true`。
