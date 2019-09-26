---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountSelection

 变量允许您根据各个页面的 URL 动态选择报表包。

>[!NOTE]
>
>`dynamicAccountSelection`无法应用于自定义链接跟踪。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | false |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

## 语法和可能值

```js
s.dynamicAccountSelection=[true|false]
```

仅允许“true”和“false”作为 *`dynamicAccountSelection`*。

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

* 动态帐户选择不受 [AppMeasurement for JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* 通常使用 [!DNL DigitalPulse Debugger] 来确定将由哪个报表包从各页面接收数据。
