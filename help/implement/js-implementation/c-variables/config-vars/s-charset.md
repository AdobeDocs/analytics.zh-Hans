---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.charSet

charSet属性通常在JavaScript文件中设置，Analytics使用它将传入数据转换为UTF-8，以便Analytics进行存储和报告。

>[!N] 注意：向多字节报表包发送数据时需要charSet属性，而且不应与标准报表包一起使用。 在标准 ISO 报表包中设置 charSet 属性可能会截断变量或意外转换字符。

charSet 属性的值应与 META 标签或 http 头中的网页编码匹配，虽然语法可能略有不同。虽然 META 标签可能会使用编码别名，但 charSet 的值应使用编码首选名称（或正式名称）。

下表列示一些常见编码以及它们的首选名称和别名。

| 首选名称 | 别名 |
|--- |--- |
| ISO-8859-1 | ISO_8859-1,CP819,latin1 |
| ISO-8859-2 | ISO_8859-2,latin2 |
| ISO-8859-5 | ISO_8859-5,cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

由于存在大量编码和别名，请联系实施顾问或Adobe客户关怀，确认charSet的正确值（如果它未出现在上表中）。

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

charSet 参数若有非空白值将导致数据转换为 UTF-8 后存储。128-255 范围的所有字符将转换为合适的 UTF-8 双字节序列并存储。这些字符在标准报表包中无法正常显示。因此，在标准报表包中不得使用 charSet 属性。

同样地，charSet 参数若为空值，将跳过数据转换过程，而 128-255 范围的所有字符将以单字节存储。由于这些字符的单字节代码在 UTF-8 中无效，所以它们无法在多字节报表包中正常显示。因此，在多字节报表包中应始终使用 charSet 参数。此外，网页编码时应使用合适的值。

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. 但是，如果页面上的变量包含非ASCII字符，则必须填 *`charSet`* 充该变量。

## 参数

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | CE | 不适用 | "" |

## 语法和可能值

```js
s.charSet="character_set"
```

## 示例

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```
