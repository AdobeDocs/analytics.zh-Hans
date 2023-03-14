---
title: abort
description: abort 变量是一个布尔值，用于阻止将点击发送到 Adobe 数据收集服务器。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 48%

---

# abort

`abort` 变量是一个布尔值，用于阻止将下一个跟踪调用发送到 Adobe。Web SDK中存在类似的功能，允许您返回 `false` 在发送XDM事件之前。

## 取消使用Web SDK扩展发送事件

使用 [!UICONTROL 在事件发送回调之前开启] 代码编辑器和返回 `false`.

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection?lang=zh-Hans)。
1. 单击所需的标记属性。
1. 转到 [!UICONTROL 扩展] 选项卡，然后单击 **[!UICONTROL 配置]** 按钮位于 [!UICONTROL Adobe Experience Platform Web SDK].
1. 下 [!UICONTROL 数据收集]，单击 **[!UICONTROL 在事件发送回调代码之前编辑]** 按钮。
1. 在代码编辑器中，将以下代码置于要中止向Edge发送数据的任何条件下：

```js
return false;
```

## 手动实施Web SDK时取消发送事件

使用 `onBeforeEventSend` 回调和返回 `false`. 参见 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 有关更多信息，请参阅Web SDK文档。

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
>`abort` 变量在每次跟踪调用后将重置为 `false`。如果需要中止同一页面上的后续跟踪调用，请再次将 `abort` 设置为 `true`。

例如， `abort` 变量可在 [`doPlugins()`](../functions/doplugins.md) 函数，在将图像请求发送到Adobe之前运行的最后一个函数。 此示例的操作方式与 `onBeforeEventSend` 使用Web SDK回调。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

您可以将用于确认您不希望跟踪的活动（如一些自定义链接或显示广告中的外部链接）的逻辑集中在一起。
