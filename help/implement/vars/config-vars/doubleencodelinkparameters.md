---
title: doubleEncodeLinkParameters
description: 启用或禁用AppMeasurement双重编码链接跟踪变量。
source-git-commit: d0e3b28590b24d630a192ee857a7d84c115dc8c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# doubleEncodeLinkParameters

此 `doubleEncodeLinkParameters` 变量是一个布尔值，可确定是否对链接跟踪变量编码一次(如果设置为 `false`)或两次(如果设置为 `true`)。 它只会影响 `linkName` (属于 [`tl()`](../functions/tl-method.md) 方法)和 [`linkURL`](linkurl.md). 它需要AppMeasurement2.23.1或更高版本才能使用。 此变量的默认值为 `true`.

在AppMeasurement的早期版本中，链接跟踪变量始终通过URL编码两次。 虽然对于通常依赖于单字节字符的实施来说，这并不是问题，但双重编码会为报表中的多字节字符创建不正确的编码值。 将此变量设置为 `false` 对链接跟踪值编码一次，这通常是所需的行为。

* 如果您的实施使用多字节字符，并且链接跟踪变量经过URL解码以偏移AppMeasurement的双重编码，则将此变量设置为 `true`. 此值将保留现有的AppMeasurement功能。
* 如果您的实施使用多字节字符，并且您未对链接跟踪值进行URL解码，则Adobe建议将此变量设置为 `false`.
* 如果您的实施不使用多字节字符，则不需要此变量。 但是，Adobe建议将此变量设置为 `false` 在可能发送多字节字符的情况下。

## 使用Web SDK对链接参数进行双重编码

此变量特定于AppMeasurement，任何类型的Web SDK实施都不需要此变量。

## 使用Adobe Analytics扩展对链接参数进行双重编码

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.doubleEncodeLinkParameters

此 `s.doubleEncodeLinkParameters` 变量是一个布尔值，用于确定是否对链接跟踪值进行双重编码。 如果未定义此变量，则其默认值为 `true` 保留现有实施的功能。 Adobe建议将此值设置为 `false` 适用于所有新实施，尤其是当您在链接跟踪报表中看到URL编码值时。

```js
s.doubleEncodeLinkParameters = false;
```