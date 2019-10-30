---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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