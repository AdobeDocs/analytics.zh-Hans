---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.useForcedLinkTracking

此标记用于禁用某些浏览器的强制链接跟踪。FireFox 20 及更高版本和 WebKit 浏览器均默认启用强制链接跟踪。

When `useForcedLinkTracking` is enabled, the AppMeasurement file overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. AppMeasurement文件执行跟踪链接调用并手动处理导航事件，而不是使用默认的浏览器操作。

在 JavaScript H.25.4（2013 年 2 月发布）中，向 `useForcedLinkTracking` 启用时所跟踪的链接添加了以下范围限制。自动强制链接跟踪仅适用于：

* `<A>` 和 `<AREA>` 标记.
* 标记必须具有 `HREF` 属性.
* The `HREF` can't start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

默认值= true

## 示例

`s.useForcedLinkTracking = false`

