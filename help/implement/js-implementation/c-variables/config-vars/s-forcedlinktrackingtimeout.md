---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forcedLinkTrackingTimeout

此值指定最大等待时间。Specifically, it sets the maximum number of milliseconds to wait for tracking to finish before performing the `doneAction` that was passed into `s.tl`. 如果跟踪链接调用在此超时期限前完成，则立即执行 `doneAction`。如果您发现跟踪链接调用没有完成，建议您提高此超时期限。

默认值= 250

示例: `s.forcedLinkTrackingTimeout = 500`
