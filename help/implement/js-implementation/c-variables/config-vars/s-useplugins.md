---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.usePlugins

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

如 [!UICONTROL 果usePlugins] 为“true”，则在每 *`s_doPlugins`* 个图像请求之前调用函数。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | True |

## 语法和可能值

```js
s.usePlugins=true|false
```

[!UICONTROL usePlugins] 变量应为“true”或“false”。

## 示例

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

如果未在 JavaScript 文件中声明 *`s_doPlugins`* function is not declared in your JavaScript file.

## 配置设置

无