---
title: decodeLinkParameters
description: 启用或禁用AppMeasurement双重编码链接跟踪变量。
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YzBsuWvpzof1f8qqJO5j8wuWvHSWdPomxowisPbkg7E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 8%

---

# decodeLinkParameters

`decodeLinkParameters`变量是一个布尔值，用于确定是否对链接跟踪变量进行编码一次（如果设置为`true`）或两次（如果设置为`false`）。 它仅影响`linkName`（[`tl()`](../functions/tl-method.md)方法的一部分）和[`linkURL`](linkurl.md)。 它需要AppMeasurement v2.24.0或更高版本才能使用。 此变量的默认值为`false`。

在v2.24.0之前的AppMeasurement版本中，链接跟踪变量始终进行URL编码两次。 虽然对于通常依赖单字节字符的实施来说，这并不是问题，但双重编码会为报表中的多字节字符创建不正确的编码值。 将此变量设置为`true`会对链接跟踪值编码一次，这通常是所需的行为。

* 如果您的实施使用多字节字符，并且链接跟踪变量经过URL解码以偏移AppMeasurement的双重编码，则将此变量设置为`false`。 此值将保留现有的AppMeasurement功能。
* 如果您的实施使用多字节字符并且您未对链接跟踪值进行URL解码，Adobe建议将此变量设置为`true`。
* 如果您的实施不使用多字节字符，则不需要此变量。 但是，Adobe建议在可能发送多字节字符的情况下将此变量设置为`true`。

## 使用Web SDK对链接参数进行双重编码

此变量专用于AppMeasurement，任何类型的Web SDK实施都不需要此变量。

## 使用Adobe Analytics扩展对链接参数进行双重编码

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.decodeLinkParameters

`s.decodeLinkParameters`变量是一个布尔值，用于确定是否对链接跟踪值进行双重编码。 如果未定义此变量，则其默认值为`false`，以保留现有实施的功能。 Adobe建议为所有新实施将此值设置为`true`，尤其是当您在链接跟踪报表中看到URL编码值时。

```js
s.decodeLinkParameters = true;
```
