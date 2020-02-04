---
title: 产品
description: 发送有关显示或购物车中的产品的数据。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# 产品

该变 `products` 量跟踪与其关联的产品和属性。 此变量通常在单个产品页面、购物车页面和购买确认页面上设置。 它是一个多值变量，这意味着您可以在同一次点击中发送多个产品，Adobe会将该值解析为单独的维值。

> [!NOTE] 如果此变量在点击中设置，而变量中没有购物车事 `events` 件，则“产品查看次数”量度将递增1。 确保每次点击时都设置了相应的购物车事件。

## Adobe Experience Platform Launch中的产品

Launch中没有专用字段来设置此变量；但是，存在多个第三方扩展以提供帮助。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩展 [!UICONTROL 功能] ”选项卡，然后单击“ [!UICONTROL 目录] ”以查看所有可用的扩展功能。
4. 搜索术语“product”，该术语显示了若干可用于帮助设置此变量的扩展。

您可以使用其中一个扩展，也可以按照下面的AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Launch自定义代码编辑器中的s.products

该变 `s.products` 量是一个字符串，每个产品包含多个分隔字段。 每个产品在所有字段中最多可包含100字节。 在字符串中用分号(`;`)分隔每个字段。

* **类别** （可选）:总体产品类别。 贵组织决定如何将产品分组到类别中。
* **产品名称** （必需）:产品的名称。
* **数量** （可选）:此产品在购物车中的数量。 此字段仅适用于购买事件的点击。
* **价格** （可选）:以小数表示的产品总价。 如果数量大于1，则将价格设置为总价，而不是单独产品价格。 对齐此值的货币以匹配变 `currencyCode` 量。 请勿在此字段中包含货币符号。 此字段仅适用于购买事件的点击。
* **事件** （可选）:与产品关联的活动。 用管道()分隔多个事`|`件。 有关更 [多信息](events/events-overview.md) ，请参阅活动。
* **eVar** （可选）:与产品绑定的销售eVar。 用管道(`|`)分隔多个销售eVar。 有关更 [多信息，请参阅销售eVar](../../../components/c-variables/c-merch-variables/var-merchandising.md) 。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

此变量支持同一点击中的多个产品。 它对于购物车和包含多种产品的购买非常有价值。 虽然每个产品有100字节的限制，但变量的总长 `products` 度为64K。 在字符串中用逗号(`,`)分隔每个产品。

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

> [!IMPORTANT] 确保从产品名称、类别和销售eVar值中清除所有分号、逗号和管道。 如果产品名称包含逗号，则AppMeasurement会将其解析为新产品的开头。 此错误解析会引发产品字符串的其余部分，导致维和报告中的数据不正确。

## 示例

在省 `products` 略字段和包括多个产品时，该变量是灵活的。 这种灵活性可能导致您容易错过分隔符，这会导致您的实施向Adobe发送错误数据。

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product,;Example product";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```
