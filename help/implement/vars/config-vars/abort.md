---
title: abort
description: abort 变量是一个布尔值，用于阻止将点击发送到 Adobe 数据收集服务器。
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 39%

---

# abort

`abort`变量是一个布尔值，用于阻止将下一个跟踪调用发送到Adobe。 Web SDK中存在类似的功能，允许您在发送XDM事件之前返回`false`。

## 使用Web SDK扩展取消发送事件

在事件发送回调[!UICONTROL 代码编辑器之前使用]On并返回`false`。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;下的[!UICONTROL 配置]按钮。
1. 在[!UICONTROL 数据收集]下，单击&#x200B;**[!UICONTROL 在事件发送回调代码之前编辑]**&#x200B;按钮。
1. 在代码编辑器中，将以下代码置于您希望中止向Edge发送数据的任何条件下：

```js
return false;
```

## 取消手动发送事件以实施Web SDK

使用`onBeforeEventSend`回调并返回`false`。 有关详细信息，请参阅Web SDK文档中的[全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## 在Adobe Analytics扩展中使用abort变量

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.abort

`s.abort` 变量是一个布尔值。其默认值为 `false`。

* 如果设置为 `true`，则下一次跟踪调用（[`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)）不会向 Adobe 发送任何数据。
* 如果设置为 `false` 或未定义，则此变量不执行任何操作。

```js
s.abort = true;
```

>[!NOTE]
>
>`abort` 变量在每次跟踪调用后将重置为 `false`。如果要中止同一页面上的后续跟踪调用，请再次将`abort`设置为`true`。

可以在`abort`函数中设置[`doPlugins()`](../functions/doplugins.md)变量，该函数是将图像请求发送到Adobe之前要运行的最后一个函数。 此示例的操作方式与使用Web SDK的`onBeforeEventSend`回调类似。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

您可以将用于确认您不希望跟踪的活动（如一些自定义链接或显示广告中的外部链接）的逻辑集中在一起。
