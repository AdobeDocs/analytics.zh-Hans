---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.forcedLinkTrackingTimeout

执行传递给 的 `s.tl`doneAction 前，等待跟踪完成的最大毫秒数。此值指定最大等待时间。如果跟踪链接调用在此超时期限前完成，则立即执行 doneAction。如果您发现跟踪链接调用没有完成，建议您提高此超时期限。

默认值= 250

示例: `s.forcedLinkTrackingTimeout = 500`
