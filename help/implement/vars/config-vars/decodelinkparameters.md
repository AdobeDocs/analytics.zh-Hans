---
title: Decodlinkparameters
description: 启用或禁用AppMeasurement双重编码链接跟踪变量。
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: 12d35a0f503ef79eabd55c169d9642c049542798
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# Decodlinkparameters

此 `decodeLinkParameters` 变量是一个布尔值，用于确定是否对链接跟踪变量进行编码一次(如果设置为 `true`)或两次(如果设置为 `false`)。 它仅影响 `linkName` (属于 [`tl()`](../functions/tl-method.md) 方法)和 [`linkURL`](linkurl.md). 它需要AppMeasurementv2.24.0或更高版本才能使用。 此变量的默认值为 `false`.

在v2.24.0之前的AppMeasurement版本中，链接跟踪变量始终进行URL编码两次。 虽然对于通常依赖单字节字符的实施来说，这并不是问题，但双重编码会为报表中的多字节字符创建不正确的编码值。 将此变量设置为 `true` 对链接跟踪值编码一次，这通常是所需的行为。

* 如果您的实施使用多字节字符，并且链接跟踪变量经过URL解码以偏移AppMeasurement的双重编码，则将此变量设置为 `false`. 此值将保留现有的AppMeasurement功能。
* 如果您的实施使用多字节字符并且您没有URL解码链接跟踪值，则Adobe建议将此变量设置为 `true`.
* 如果您的实施不使用多字节字符，则不需要此变量。 但是，Adobe建议将此变量设置为 `true` 在可能发送多字节字符的情况下。

## 使用Web SDK对链接参数进行双重编码

此变量专用于AppMeasurement，任何类型的Web SDK实施都不需要此变量。

## 使用Adobe Analytics扩展对链接参数进行双重编码

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.decodeLinkParameters

此 `s.decodeLinkParameters` 变量是一个布尔值，用于确定是否对链接跟踪值进行双重编码。 如果未定义此变量，则其默认值为 `false` 保留现有实施的功能。 Adobe建议将此值设置为 `true` 适用于所有新实施，尤其是当您在链接跟踪报表中看到URL编码值时。

```js
s.decodeLinkParameters = true;
```
