---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

 变量是以逗号隔开的文件扩展名列表。

如果您网站上包含的链接可转到具有任何此类扩展名的文件，则这些链接的 URL 会在[!UICONTROL 文件下载]报表中显示。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | 不适用 | “流量”&gt;“网站流量”&gt;“文件下载” | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

只有当 *`linkDownloadFileTypes`* 设置为“True”时，*`trackDownloadLinks`* 变量才相关。

只有在链接上单击鼠标左键才会计入[!UICONTROL 文件下载]报表。在页面加载时自动启动的所有文件下载，或仅在重定向后启动的下载，不会计入[!UICONTROL 文件下载]报表。当您右键单击某文件并选择“将目标另存为...”选项时，不会将它计入[!UICONTROL 文件下载]报表。

*`linkDownloadFileTypes`*&#x200B;变量可用于跟踪 RSS 馈送的点击量。如果您具有指向扩展名为 .xml 或其他的 RSS 馈送的链接，则在 *`linkDownloadFileTypes`* 列表后附加“.xml”可让您查看点击每个 RSS 链接的频率。

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

参数 `trackDownloadLinks` 和 `trackExternalLinks` 可确定是否启用自动文件下载和退出链接跟踪。启用后，若任何链接的文件类型与 `linkDownloadFileTypes` 中的任一值相匹配，则会自动将该链接作为文件下载进行跟踪。若任何链接的 URL 不包含 `linkInternalFilters` 中的任一值，则会自动将该链接作为退出链接进行跟踪。

在 JavaScript H.25.4（2013 年 2 月发布）中，更新了自动退出链接跟踪，以始终忽略 `HREF` 属性以 `#`、`about:` 或 `javascript:` 开头的链接。

### 示例 1

文件类型 `.jpg` 和 `.aspx` 未包含在上述 `linkDownloadFileTypes` 中，因此不会自动将对这两种文件类型的点击作为文件下载来进行跟踪和报告。

参数 `linkLeaveQueryString` 可修改用于确定退出链接的逻辑。当 `linkLeaveQueryString`=false 时，将仅使用链接 URL 的域、路径和文件部分来确定退出链接。当 `linkLeaveQueryString`=true 时，还将使用链接 URL 的查询字符串部分来确定退出链接。

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

*注意：单个链接只可作为文件下载或退出链接进行跟踪，且优先作为文件下载。如果根据参数`linkDownloadFileTypes`和`linkInternalFilters`，某个链接既是退出链接又是文件下载，则会将该链接作为文件下载，而不是退出链接来进行跟踪和报告。*