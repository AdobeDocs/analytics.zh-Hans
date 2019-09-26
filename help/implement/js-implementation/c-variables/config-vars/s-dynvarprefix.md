---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

 变量允许部署应当动态填充的标记变量。

Cookie、请求头和图像查询字符串参数均适用于动态填充。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | D= | 任何 | D= |

## 语法和可能值

```js
s.prop1="D=User-Agent”
```

或将自定义标记应用于动态变量

```js
s.dynamicVariablePrefix=".."
```

## 示例

```js
s.prop1="D=User-Agent”
```

或将自定义标记应用于动态变量

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## 缺陷、问题和提示

* 动态变量可通过将值复制到其他变量，大幅缩短 URL 的总长度。

* 动态变量可用于收集头及 Cookie 中的数据（而这些数据是无法通过其他数据收集方式获得的）。
