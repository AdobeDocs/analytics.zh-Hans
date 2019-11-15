---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackDownLoadLinks

如果希望跟踪网站上可下载文件的连接，请将 设置为“true”。

如果 *`trackDownloadLinks`* 为“true”，则使用 *`linkDownloadFileTypes`* 来确定哪些链接是可下载文件。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | true |

如果没有指向网站上可下载文件的链接，或者不想跟踪可下载文件的点击次数，则应将&#x200B;*`trackDownloadLinks`*&#x200B;变量设置为“false”。如果 *`trackDownloadLinks`* 为“true”，则点击文件下载链接时，会将数据立即发送至 [!DNL Analytics]。与下载链接一起发送的数据包括链接下载 URL 以及该链接的访客点击图数据。如果 *`trackDownloadLinks`* 为“false”，则网站上可下载文件链接的访客点击图可能会被少报。

## 语法和可能值

*`trackDownloadLinks`变量应为“true”或“false”。*

## 示例

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## 配置设置

无

## 缺陷、问题和提示

* 当 *`trackDownloadLinks`* 为“false”时，用户用于下载网站上文件的链接可能会在访客点击图中被少报。

* 当 *`trackDownloadLinks`* 为“true”，访客每次点击文件下载链接时都会发送数据。

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