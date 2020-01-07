---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---



# s.linkInternalFilters

 变量用于确定您网站中哪些链接为退出链接。

它是以逗号隔开的过滤器列表，显示属于网站一部分的链接。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | “路径”&gt;“登录和退出”&gt;“退出链接” |  |

> [!NOTE]我们之前建议将 linkInternalFilters 设置为 Javascript:。但是，这导致所有的域（包括标签当前所在的域）都被视为外部域。因此，如果您想让一些域被视为内部域，则可以添加一些内容，如以下示例所示。

*`linkInternalFilters`* 变量用于确定链接是否为退出链接。根据定义，退出链接是将访客带离您网站的任何链接。无论退出链接的目标窗口是弹出窗口还是现有窗口，都不会影响该链接在退出链接报表中的显示。如果 *`trackExternalLinks`* 设置为 `"true"`。（有关 DTM 如何处理退出链接的信息，请参阅“动态标签管理”文档中的[链接跟踪](https://marketing.adobe.com/resources/help/zh_CN/dtm/link_tracking.html)。）*`linkInternalFilters`* 中的过滤器不区分大小写。

默认情况下，*`linkInternalFilters`* 中的过滤器列表适用于任何链接的域和路径。如果将 *`linkLeaveQueryString`* 设置为 `"true"`，则这些过滤器应用于整个 URL（域名、路径和查询字符串）。过滤器通常应用于 URL 的绝对路径，即使将相对路径用作 href 值也不例外。

请小心确认您网站的所有域名（以及使用您的 JavaScript 文件的任何合作伙伴）都包含在 *`linkInternalFilters`*。如果列表中未包含所有的域名，则未包含的域名的所有相关链接都将被视为退出链接，这会增加所发送的服务器调用次数。如果您希望多个域或公司使用单个 [!DNL AppMeasurement] for JavaScript 文件，则可以考虑在页面上填充 *`linkInternalFilters`*，覆盖 JavaScript 文件中指定的值。如果您有立刻重定向到主域的虚域，则无需将这些虚域加入此列表。

以下示例说明此变量的使用方法。在此示例中，页面的 URL 是 `https://www.mysite.com/index.html`。

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## 语法和可能值

*`linkInternalFilters`* 变量是以逗号隔开的 ASCII 字符列表。不允许有空格。

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## 示例

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## 配置设置

无

## 缺陷、问题和提示

* 包括过滤器列表下可能提供 [!DNL AppMeasurement] for JavaScript 文件的所有域。
* 定期检查“[!UICONTROL 路径]”&gt;“[!UICONTROL 登入和退出]”&gt;“[!UICONTROL 退出]”链接报表，以确保报表中的所有条目正确无误。

* 定期检查合作伙伴合同，以确定它们是否包含关于链接跟踪的限制。例如，系统可能会禁止跟踪链接在合作伙伴显示广告中显示。通过将合作伙伴的域加入 *`linkInternalFilters`* 来过滤合作伙伴链接：

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

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
