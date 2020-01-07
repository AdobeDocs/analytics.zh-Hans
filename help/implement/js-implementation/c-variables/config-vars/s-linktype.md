---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: 21f278017472ae39c6066ca7694a5cdbbfde41f3

---


# s.linkType

包含自动确定的链接类型（如果有）。可设置为以下值之一：

    * `d`（下载）
    * `e`（退出）
    * `o`（自定义/其他）

此为图像请求中的 `pe` 参数。如果通过 [`linkURL`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkURL.html) 或 [`linkName`](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html) 设置，则服务器调用将作为下载、自定义或退出链接发送。

*注意：无法为文件下载、退出链接或自定义链接设置变量[`pageName`](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)，因为每种链接类型都并非页面查看，因此没有关联的页面名称。*


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
