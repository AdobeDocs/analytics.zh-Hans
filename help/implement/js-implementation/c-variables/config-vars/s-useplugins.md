---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.usePlugins

如果该函数可用，并且包含有用的代码，则应将 [!UICONTROL s_usePlugins] 设置为“true”。

如果 [!UICONTROL usePlugins] 为“true”，则在每个图像请求之前调用 *`s_doPlugins`* 函数。

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

如果未在 JavaScript 文件中声明 *`s_doPlugins`* 函数，则 [!UICONTROL usePlugins] 变量只应为 false（或未声明）。

## 配置设置

无
