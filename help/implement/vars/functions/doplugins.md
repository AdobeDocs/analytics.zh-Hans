---
title: doPlugins
description: 在编译点击并将其发送到 Adobe 之前配置逻辑。
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 63%

---

# doPlugins

`doPlugins` 变量会用作“最后一次调用”，以便在您的实施中设置值。它是调用[插件方法](../plugins/impl-plugins.md)并在发送图像请求之前设置任何所需变量的理想场所。 如果启用了 [`usePlugins`](../config-vars/useplugins.md)，它将在编译任何类型的图像请求并将其发送到 Adobe 之前自动运行，包括：

* 所有页面查看 ([`t()`](t-method.md)) 调用
* 所有链接跟踪 ([`tl()`](tl-method.md)) 调用，包括自动下载链接和退出链接

在编译图像请求并将其发送到 Adobe 之前，使用 `doPlugins` 变量调用插件代码并设置最终变量值。

## 使用Web SDK扩展的“在事件之前发送”回调代码

Web SDK使用具有类似功能的`doPlugins`，而不是`onBeforeEventSend`。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;下的[!UICONTROL 配置]按钮。
1. 在[!UICONTROL 数据收集]下，单击&#x200B;**[!UICONTROL 在事件发送回调代码之前编辑]**&#x200B;按钮。
1. 将所需的代码置于编辑器中。

## 使用`onBeforeEventSend`手动实施Web SDK

Web SDK使用具有类似功能的`doPlugins`，而不是`onBeforeEventSend`。 有关详细信息，请参阅Web SDK文档中的[全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## 使用Adobe Analytics扩展的插件

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

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
