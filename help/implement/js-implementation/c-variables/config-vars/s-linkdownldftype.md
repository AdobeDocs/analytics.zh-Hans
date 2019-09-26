---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkDownloadFileTypes

 变量是以逗号隔开的文件扩展名列表。

如果您网站上包含的链接可转到具有任何此类扩展名的文件，则这些链接的 URL 会在[!UICONTROL 文件下载]报表中显示。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | 不适用 | “流量”&gt;“网站流量”&gt;“文件下载” | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

The 变 *`linkDownloadFileTypes`* 量仅在设置为“ *`trackDownloadLinks`* True”时才相关。

只有在链接上单击鼠标左键才会计入[!UICONTROL 文件下载]报表。在页面加载时自动启动的所有文件下载，或仅在重定向后启动的下载，不会计入[!UICONTROL 文件下载]报表。当您右键单击某文件并选择“将目标另存为...”选项时，不会将它计入[!UICONTROL 文件下载]报表。

The *`linkDownloadFileTypes`*&#x200B;变量可用于跟踪 RSS 馈送的点击量。如果您有带。xml或其他扩展名的RSS源链接，则在列表后面附加“,xml” *`linkDownloadFileTypes`* 可查看每个RSS链接的单击频率。

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