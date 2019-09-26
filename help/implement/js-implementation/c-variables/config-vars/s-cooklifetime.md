---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieLifetime

 变量由 JavaScript 和数据收集服务器用来确定 Cookie 的有效期。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | cl | “流量”&gt;“技术”&gt;“Cookie”所有与访客有关的报表 | "" |

如果设置了&#x200B;*`cookieLifetime`*，它会覆盖 JavaScript 和数据收集服务器的任何其他 Cookie 过期日期，但有一种情况除外，下文对此进行了介绍。The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookie
* Cookie
* JavaScript 设置和插件

## 语法和可能值

```js
s.cookieLifetime="value"
```

可能值如下所示：

* ""
* "NONE"
* "SESSION"
* 表示过期前剩余秒数的整数

## 示例

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## 配置设置

无

## 缺陷、问题和提示

*`cookieLifetime`* 影响跟 [!DNL Analytics] 踪。 If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. 务请小心设置 *`cookieLifetime`*.
