---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.currencyCode

 变量确定收入使用的兑换率。

所有货币额都是以您选择的货币进行存储的。如果该货币与 *`currencyCode`* 中指定的货币相同，或者 *`currencyCode`* 为空，则不应用任何转化。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | cc | “转化”&gt;“购买”&gt;“收入” 显示收入或货币值的所有转化报表 | "USD" |

如果网站允许访客以多种货币购买，则应使用&#x200B;*`currencyCode`*&#x200B;变量以确保收入以相应的货币进行存储。例如，如果报表包的本位币为 USD，而您以 40 欧元售出了一件商品，则在 HTML 页面中应使用“EUR”填充 *`currencyCode`*。数据收集接收到数据后，将使用货币兑换率将 40 欧元兑换为等值的美元。

如果支持以多种货币销售，则建议填充 HTML 页面中的&#x200B;*`currencyCode`*&#x200B;变量，而不是 JavaScript 文件中的变量。如果要使用自己的兑换率而不是 Adobe 使用的兑换率，请将 *`currencyCode`* 设置为等于报表包的基本货币。然后在将收入发送到 [!DNL Analytics] 之前兑换所有收入。

货币兑换适用于收入和任何货币事件。这些事件用于计算与收入类似的值的总和，例如税款和运输费用。收入和货币事件在产品字符串中指定。有关产品的详细信息，请参阅 [events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html).

## 语法和可能值

```js
s.currencyCode="currency_code"
```

## 示例

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## 配置设置

Adobe [!DNL Customer Care] 可以更改报表包的默认货币设置。更改报表包的本位币时，不会兑换系统中的现有收入，但会相应地兑换所有新收入值。

## 缺陷、问题和提示

* 如果您发现报表中的收入量大得惊人，请确保正确设置了 *`currencyCode`* 变量和报表包的基本位币。
* *`currencyCode`* 为非永久性变量，即该变量必须在同一图像请求中以任何收入或其他货币相关量度的方式进行传递。
* 货币事件不应用于非货币用途。如需计算非货币的任意值或动态值，请使用[!UICONTROL 数值]事件类型。
* 在&#x200B;*`currencyCode`*&#x200B;变量为空时，不会发生兑换。

有关详细信息，请参阅 [货币代码](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html)。
