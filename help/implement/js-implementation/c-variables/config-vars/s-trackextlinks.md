---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
