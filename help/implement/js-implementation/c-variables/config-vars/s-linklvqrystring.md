---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkLeaveQueryString

默认情况下，查询字符串被排除在所有报表之外。

对于一些退出链接和下载链接而言，URL 的重要部分可能位于查询字符串中，如下面的示例 URL 中所示。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

下载文件名称可在查询字符串中定义，因而查询字符串对于提高[!UICONTROL 文件下载]报表的准确度是必需的。

*`linkLeaveQueryString`*&#x200B;变量确定[!UICONTROL 退出链接]和[!UICONTROL 文件下载]报表中是否包含查询字符串。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | 不适用 | 退出链接文件下载 | false |

*注意：`linkLeaveQueryString=true`设置可包含所有退出链接和下载链接的全部查询字符串参数。*

## 语法

```js
s.linkLeaveQueryString=[false/true]
```

## 示例

```js
s.linkLeaveQueryString=false
```

## 可能值

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## 配置设置

此变量不需要任何配置。

## 缺陷、问题和提示

* 设置 `s.linkLeaveQueryString=true` 可包含所有退出链接和下载链接的全部查询字符串参数。
* `linkLeaveQueryString` 变量不会影响记录的页面 URL、访客点击图或[!UICONTROL 路径]报表。

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