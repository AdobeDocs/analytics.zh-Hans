---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: ht
source-git-commit: 1773e84809e04b3be25c77bf1fb8ad8317b7f8c0

---


# s-linkURL

链接的 URL，当 `linkName` 不存在时用作名称。可设置为任何 URL 字符串。此为图像请求中的 `pev1` 参数。


如果通过 [`linkType`](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) 设置，则图像请求将作为下载、自定义或退出链接发送。


**示例**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```
