---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.dynamicAccountSelection

 变量允许您根据各个页面的 URL 动态选择报表包。

> [!NOTE]`dynamicAccountSelection`无法应用于自定义链接跟踪。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | false |

> [!NOTE]如果未声明 `dynamicAccountList` 变量或将该变量设置为“False”，则 `dynamicAccountMatch` 和 `dynamicAccountSelection` 都会被忽略。

## 语法和可能值

```js
s.dynamicAccountSelection=[true|false]
```

 *`dynamicAccountSelection`*.

## 示例

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## 配置设置

无

## 缺陷、问题和提示

* [AppMeasurement for JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) 不支持动态帐户选择。

* 通常使用 [!DNL DigitalPulse Debugger] 来确定将由哪个报表包从各页面接收数据。
