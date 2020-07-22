---
title: 产品
description: 发送有关所显示产品或购物车中产品的数据。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 87%

---


# 产品

`products` 变量会跟踪与其关联的产品和属性。此变量通常在单个产品页面、购物车页面和购买确认页面上设置。它是一个多值变量，这意味着您可以在同一次点击中发送多个产品，Adobe会将该值解析为单独的维度项目。

>[!NOTE]
>
>If this variable is set in a hit without a shopping cart event in the [`events`](events/events-overview.md) variable, the [Product Views](/help/components/metrics/product-views.md) metric increments by 1. 确保使用变量对每次点击设置适当的购物车事件 `products` 符。

## Adobe Experience Platform Launch 中的产品

Launch 中没有专门用于设置此变量的字段；但是，存在多个第三方扩展可帮助进行此设置。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]以查看所有可用的扩展。
4. 搜索术语“product”，结果会显示若干可用于设置此变量的扩展。

您可以使用其中一个扩展，也可以按照下面的 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.products

`s.products` 变量是一个字符串，其中包含每个产品的多个分隔字段。每个产品在所有字段中最多可包含 100 字节。在字符串中使用分号 (`;`) 分隔每个字段。

* **类别**（可选）：总体产品类别。贵组织可决定如何划分产品类别。
* **产品名称**（必需）：产品的名称。
* **数量**（可选）：购物车中此产品的数量。此字段仅适用于具有购买事件的点击。
* **价格**（可选）：以小数表示的产品总价格。如果数量大于 1，则将价格设置为总价，而不是产品单价。调整此值的货币以与 [`currencyCode`](../config-vars/currencycode.md) 变量匹配。请勿在此字段中包含货币符号。此字段仅适用于具有购买事件的点击。
* **事件**（可选）：与产品绑定的事件。使用管道字符 (`|`) 分隔多个事件。有关更多信息，请参阅[事件](events/events-overview.md)。
* **eVar**（可选）：与产品绑定的推销 eVar。使用管道字符 (`|`) 分隔多个推销 eVar。有关更多信息，请参阅[推销 eVar ](evar-merchandising.md)。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

此变量在同一点击中支持多个产品。它对于购物车和包含多种产品的购买非常有用。虽然每个产品具有 100 字节的限制，但 `products` 变量的总长度为 64 K。在字符串中使用逗号 (`,`) 分隔每个产品。

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

>[!IMPORTANT]
>
> 从产品名称、类别和推销 eVar 值中去除所有分号、逗号和管道字符。如果产品名称包含逗号，则 AppMeasurement 会将其解析为新产品的开头。此错误解析会丢掉产品字符串的其余部分，导致维度和报表中的数据不正确。

## 示例

当省略字段并包含多个产品时，`products` 变量会非常灵活。这种灵活性可能会使您容易丢失分隔符，从而导致您的实施向 Adobe 发送错误数据。

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

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
