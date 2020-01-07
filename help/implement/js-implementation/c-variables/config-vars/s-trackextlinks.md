---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackExternalLinks

如果为“true”，则用于确定所点击的链接是否为退出链接。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | true |

如果没有指向网站上可下载文件的链接，或者不想跟踪可下载文件的点击次数，则应将&#x200B;*`trackExternalLinks`*&#x200B;变量仅设置为“false”。退出链接为任何让访客退出网站的链接。如果将 *`trackExternalLinks`* 为“true”，则点击退出链接时，会立即发送跟踪数据。随退出链接一起发送的数据包括链接 URL、链接名称和该链接的访客 ClickMap 数据。如果将 *`trackExternalLinks`* 为“false”，则网站上退出链接的访客点击图数据可能会少报。

## 语法和可能值

*`trackExternalLinks`变量应为“true”或“false”。*

```
js
s.trackExternalLinks=true|false
```

## 示例

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## 配置设置

无

## 缺陷、问题和提示

* 当 *`trackExternalLinks`* 为“false”时，使访客从网站退出的链接在访客点击图中可能会少报。

* 当 *`trackExternalLinks`* 为“true”时，访客每次点击退出链接时（在目标链接加载前），都会发送数据。

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

在 JavaScript H.25.4（2013 年 2 月发布）中，更新了自动退出链接跟踪，以始终忽略 `HREF` 属性以 `#`、`about:` 或 `javascript:` 开始的链接。

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