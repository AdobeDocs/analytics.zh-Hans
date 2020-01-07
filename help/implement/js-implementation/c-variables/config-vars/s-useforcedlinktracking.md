---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: 8deec068fcea49f1183633826d5ce8271fb38a14

---



# s.useForcedLinkTracking

此标记用于禁用某些浏览器的强制链接跟踪。FireFox 20 及更高版本和 WebKit 浏览器均默认启用强制链接跟踪。

启用 `useForcedLinkTracking` 后，AppMeasurement 文件会覆盖某些浏览器上的默认链接行为，以防止打开新页面时跟踪链接调用被取消。AppMeasurement 文件可手动执行跟踪链接调用并处理导航事件，而不使用默认浏览器操作。

在 JavaScript H.25.4（2013 年 2 月发布）中，向 `useForcedLinkTracking` 启用时所跟踪的链接添加了以下范围限制。自动强制链接跟踪仅适用于：

* `<A>` 和 `<AREA>` 标记。
* 标记必须具有 `HREF` 属性。
* `HREF` 不得以 `#`、`about:` 或 `javascript:` 开头。
* 不得设置 `TARGET` 属性，否则 `TARGET` 需要引用当前窗口（`_self`、`_top` 或 `window.name` 的值）。

默认值 = `true`

## 示例

`s.useForcedLinkTracking = false`
