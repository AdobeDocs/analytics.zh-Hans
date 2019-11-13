---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkType

包含自动确定的链接类型（如果有）。可设置为以下值之一：

    * "d`（下载）
    * "e`（退出）
    * "o`（自定义／其他）

此为图像请求中的 `pe` 参数。如果通过 `linkURL` 或 `linkName` 设置，则服务器调用将作为下载、自定义或退出链接发送。

*注意：无法[`pageName`](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)为文件下载、退出链接或自定义链接设置变量，因为每种链接类型不是页面视图，也没有关联的页面名称。*


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
