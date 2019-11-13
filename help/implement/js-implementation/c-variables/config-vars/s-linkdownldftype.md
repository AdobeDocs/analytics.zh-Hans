---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkDownloadFileTypes

 变量是以逗号隔开的文件扩展名列表。

如果您网站上包含的链接可转到具有任何此类扩展名的文件，则这些链接的 URL 会在[!UICONTROL 文件下载]报表中显示。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | 不适用 | “流量”&gt;“网站流量”&gt;“文件下载” | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

The只有当 *`linkDownloadFileTypes`* 设置为“True”时，*`trackDownloadLinks`* 变量才相关。

只有在链接上单击鼠标左键才会计入[!UICONTROL 文件下载]报表。在页面加载时自动启动的所有文件下载，或仅在重定向后启动的下载，不会计入[!UICONTROL 文件下载]报表。当您右键单击某文件并选择“将目标另存为...”选项时，不会将它计入[!UICONTROL 文件下载]报表。

The *`linkDownloadFileTypes`*&#x200B;变量可用于跟踪 RSS 馈送的点击量。如果您具有指向扩展名为 .xml 或其他的 RSS 馈送的链接，则在 *`linkDownloadFileTypes`* 列表后附加“.xml”可让您查看点击每个 RSS 链接的频率。

## 语法和可能值

只包含文件扩展名（无空格）。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

列表中可包含任意文件扩展名。注意不要在 *`linkDownloadFileTypes`*。这样做会导致每次点击时发送额外的图像请求，从而产生主服务器调用计费。

## 示例

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## 配置设置*

无

## 缺陷、问题和提示

* 只有左键单击下载文件会导致 URL 在[!UICONTROL 文件下载]报表中显示。
* 在&#x200B;*`linkDownloadFileTypes`*&#x200B;中包含常用文件扩展名可能会显著增加发送到 Adobe 服务器的总服务器调用次数。
* 指向服务器端重定向页面或 HTML 页面自动下载文件的链接不会被计入文件下载报表，除非其文件扩展名包含在 *`linkDownloadFileTypes`*.
* 使用 JavaScript 的链接（如 javascript:openLink( )）不会被计入文件下载中。

## 退出链接和文件下载的自动跟踪

您可根据定义文件下载文件类型和退出链接的参数配置 JavaScript 文件，以自动跟踪文件下载和退出链接。

控制自动跟踪的参数如下所示：

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

参数 `trackDownloadLinks` and `trackExternalLinks` determine if automatic file download and exit link tracking are enabled. 启用后，任何文件类型与中某个值匹配的链接 `linkDownloadFileTypes` 都会作为文件下载自动跟踪。 任何包含URL且其中不包含其中某个值的链接都会 `linkInternalFilters` 作为退出链接自动跟踪。

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

### 示例 1

上述文件类 `.jpg` 型和 `.aspx` 不包括在内，因此 `linkDownloadFileTypes` 不会自动跟踪和报告对它们的单击作为文件下载。

The parameter `linkLeaveQueryString` modifies the logic used to determine exit links. When `linkLeaveQueryString`=false, exit links are determined using only the domain, path, and file portion of the link URL. When `linkLeaveQueryString`=true, the query string portion of the link URL is also used to determine an exit link.

### 示例 2

使用下列设置时，以下示例将计为退出链接：

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### 示例 3

使用下列设置时，以下链接不会计为退出链接：

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*注意：单个链接只可作为文件下载或退出链接进行跟踪，且优先作为文件下载。如果某个链接是基于参数的退出链接和文件下载，则该链接将作为文件下载而不是退出链`linkDownloadFileTypes`接`linkInternalFilters`被跟踪和报告。*