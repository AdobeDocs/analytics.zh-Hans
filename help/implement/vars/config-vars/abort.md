---
title: 中止
description: 中止变量是一个布尔值，它可阻止将点击发送到Adobe数据收集服务器。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# 中止

该 `abort` 变量是一个布尔值，它可阻止向Adobe发送下一个跟踪调用。

## 在Adobe Experience Platform Launch中使用中止变量

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## Launch中的AppMeasurement语法和自定义代码编辑器

该 `abort` 变量是布尔值。 Its default value is `false`.

* 如果设置为， `true`则下一次跟踪调用(`t()` 或 `tl()`)不会向Adobe发送任何数据。
* 如果设置为 `false` 或未定义，则此变量不执行任何操作。

```js
s.abort = true;
```

> [!NOTE] 该变 `abort` 量将重置为 `false` 每次跟踪调用之后。 如果需要中止同一页面上的后续跟踪调用，请再次 `abort` 设置为 `true` 此值。

## 示例

可 `abort` 以在函数中设置变量，该函 `doPlugins()` 数是向Adobe发送图像请求之前要运行的最后一个函数。

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

您可以集中使用的逻辑来标识您不想跟踪的活动，例如展示广告中的一些自定义链接或外部链接。
