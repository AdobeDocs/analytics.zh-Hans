---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackInlineStats

 变量可用于确定是否收集 ClickMap 数据。

如果 *`trackInlineStats`* 为“true”，则有关所点击页面及链接的数据将存储在名为 s_sq 的 Cookie 中。如果为“false”，则 s_sq 的值为“[[B]]”（一般为空）。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | ClickMap | false |

## 语法和可能值

```
js
s.trackInlineStats=true|false
```

*`trackInlineStats`变量应为“true”或“false”。*

## 示例

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## 配置设置

无
