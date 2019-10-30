---
description: 验证是否正确从页面中引用 .JS 文件。路径可指定为与当前文档相关，或使用一个绝对路径名称。
keywords: Analytics 实施
seo-description: 验证是否正确从页面中引用 .JS 文件。路径可指定为与当前文档相关，或使用一个绝对路径名称。
seo-title: JavaScript JS 文件
solution: Analytics
title: JavaScript JS 文件
topic: 开发人员和实施
uuid: 6e83223f-2127-41d3-9806-bd085fa2a747
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript JS 文件

验证是否正确从页面中引用 .JS 文件。路径可指定为与当前文档相关，或使用一个绝对路径名称。

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

如果网站的某些页面在安全协议 (https:) 中加载，并引用 JavaScript 文件的 [!DNL AppMeasurement]，请确保对该文件的引用是安全的（通过 https:），或使用以下引用代码。此示例采用了当前页面的协议，并可防止出现“某些元素不太安全”的警告。

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

请确保已正确设置 Web 服务器上的 [!DNL .JS] 文件权限，以便网站访客能够顺利下载和执行文件。如果开发服务器上使用了不同的 [!DNL .JS] 文件，请将生产服务器上的 [!DNL .JS] 文件设置为“只读”属性，以避免发生覆盖。如有更改，请确保已正确设置 [!DNL .JS] 文件顶部的以下设置：

```js
/************************** CONFIG SECTION **************************/
/* You may add or alter any code config here.                       */
/* Link Tracking Config */
s.trackDownloadLinks=false /* true for download tracking */
s.trackExternalLinks=false /* true for exit link tracking */
s.trackInlineStats=false /* true for ClickMap support */
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls"
s.linkInternalFilters="javascript:"
s.linkLeaveQueryString=false
s.linkTrackVars="None" 
s.linkTrackEvents="None"
```

如果“*`s_account`*”在 [!DNL .JS] 文件的顶部被指定了一个值，请确保报表包 ID（在 [!UICONTROL s_account] 变量中填充）正确无误。同时还要确保页面中的代码未设置[!UICONTROL 报表包 ID]（*`s_account`* 变量）。

检查图像请求和变量，以确保“回退方法”（上面示例中“拆分”代码的第三部分）未创建的是图像请求，而非 [!DNL .JS] 文件。这是可以确定的，因为“回退”方法只能创建具有最少量信息的图像请求。
