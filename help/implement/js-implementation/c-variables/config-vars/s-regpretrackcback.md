---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.registerPreTrackCallback和s.registerPostTrackCallback

这些函数的参数是：“callback”（一个函数）以及“callback”函数包含的参数。例如：

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

注册 callback 时，可通过 `requestUrl` 以及传递的任何参数来调用 callback。根据用来注册 callback 的方法，调用操作可以在跟踪调用之前或跟踪调用之后发生

无法保证调用这些 callback 的顺序。当创建了最终跟踪 URL 后，将调用在 pre 函数中注册的 callback。如果是成功的跟踪调用，则调用 post callback（若跟踪调用失败，则不调用这些函数）。`registerPreTrackCallback` 中注册的任何 callback 都不会影响跟踪调用。此外，不建议在任何已注册的 callback 中调用任何跟踪方法，因为这可能会导致无限循环。
