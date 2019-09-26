---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackDownLoadLinks

如果希望跟踪网站上可下载文件的连接，请将 设置为“true”。

If  is 'true,'  is used to determine which links are downloadable files.*`trackDownloadLinks`**`linkDownloadFileTypes`*

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | true |

如果没有指向网站上可下载文件的链接，或者不想跟踪可下载文件的点击次数，则应将&#x200B;*`trackDownloadLinks`*&#x200B;变量设置为“false”。If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. 与下载链接一起发送的数据包括链接下载 URL 以及该链接的访客点击图数据。如果 *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

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

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.

* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.