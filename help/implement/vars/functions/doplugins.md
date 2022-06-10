---
title: doPlugins
description: 在编译点击并将其发送到 Adobe 之前配置逻辑。
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 57%

---

# doPlugins

`doPlugins` 变量会用作“最后一次调用”，以便在您的实施中设置值。如果启用了 [`usePlugins`](../config-vars/useplugins.md)，它将在编译任何类型的图像请求并将其发送到 Adobe 之前自动运行，包括：

* 所有页面查看 ([`t()`](t-method.md)) 调用
* 所有链接跟踪 ([`tl()`](tl-method.md)) 调用，包括自动下载链接和退出链接

在编译图像请求并将其发送到 Adobe 之前，使用 `doPlugins` 变量调用插件代码并设置最终变量值。

## 使用Web SDK扩展在事件发送回调代码之前使用

而不是 `doPlugins`,Web SDK使用 `onBeforeEventSend` 功能相似。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
1. 单击所需的标记属性。
1. 转到 [!UICONTROL 扩展] ，然后单击 **[!UICONTROL 配置]** 按钮 [!UICONTROL Adobe Experience Platform Web SDK].
1. 在 [!UICONTROL 数据收集]，请单击 **[!UICONTROL 在事件发送回调代码之前编辑]** 按钮。
1. 将所需的代码放入编辑器中。

## 使用 `onBeforeEventSend` 手动实施Web SDK

而不是 `doPlugins`,Web SDK使用 `onBeforeEventSend` 功能相似。 请参阅 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) （位于Web SDK文档中）以了解更多信息。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## 使用Adobe Analytics扩展的插件

Adobe Analytics扩展中没有可使用此变量的专用字段。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和自定义代码编辑器中的 s.doPlugins

将 `s.doPlugins` 变量设置为包含所需代码的函数。当您进行跟踪调用时，该函数会自动运行。

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>在您的实施中仅一次将函数设置为 `doPlugins` 变量。如果多次设置 `doPlugins` 变量，则仅会使用最新的代码。

## 示例

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>AppMeasurement 的先前版本具有的 `doPlugins()` 代码略有不同。Adobe 建议将上述格式作为最佳实践。
