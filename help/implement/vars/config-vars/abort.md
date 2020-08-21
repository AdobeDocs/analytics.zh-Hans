---
title: abort
description: abort 变量是一个布尔值，用于阻止将点击发送到 Adobe 数据收集服务器。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '183'
ht-degree: 100%

---


# abort

`abort` 变量是一个布尔值，用于阻止将下一个跟踪调用发送到 Adobe。

## 在 Adobe Experience Platform Launch 中使用 abort 变量

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## Launch 中的 AppMeasurement 语法和自定义代码编辑器

`abort` 变量是一个布尔值。其默认值为 `false`。

* 如果设置为 `true`，则下一次跟踪调用（[`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)）不会向 Adobe 发送任何数据。
* 如果设置为 `false` 或未定义，则此变量不执行任何操作。

```js
s.abort = true;
```

>[!NOTE]
>
>`abort` 变量在每次跟踪调用后将重置为 `false`。如果需要中止同一页面上的后续跟踪调用，请再次将 `abort` 设置为 `true`。

## 示例

可以在 [`doPlugins()`](../functions/doplugins.md) 函数中设置 `abort` 变量，该函数是在向 Adobe 发送图像请求之前要运行的最后一个函数。

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

您可以将用于确认您不希望跟踪的活动（如一些自定义链接或显示广告中的外部链接）的逻辑集中在一起。
