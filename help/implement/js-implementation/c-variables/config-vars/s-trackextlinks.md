---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackExternalLinks

如果为“true”，则用于确定单击的任何链接是否为退出链接。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | true |

如果没有指向网站上可下载文件的链接，或者不想跟踪可下载文件的点击次数，则应将&#x200B;*`trackExternalLinks`*&#x200B;变量仅设置为“false”。退出链接为任何让访客退出网站的链接。如果将 *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. 随退出链接一起发送的数据包括链接 URL、链接名称和该链接的访客 ClickMap 数据。如果将 *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

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

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.

* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).
