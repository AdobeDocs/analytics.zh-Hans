---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkLeaveQueryString

默认情况下，查询字符串被排除在所有报表之外。

对于一些退出链接和下载链接而言，URL 的重要部分可能位于查询字符串中，如下面的示例 URL 中所示。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

下载文件名称可在查询字符串中定义，因而查询字符串对于提高[!UICONTROL 文件下载]报表的准确度是必需的。

The *`linkLeaveQueryString`*&#x200B;变量确定[!UICONTROL 退出链接]和[!UICONTROL 文件下载]报表中是否包含查询字符串。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | 不适用 | Exit Links File Downloads | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

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

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.
