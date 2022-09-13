---
title: 产品
description: 发送有关所显示产品或购物车中产品的数据。
feature: Variables
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
source-git-commit: 5b426c0cc6f0a30c167f35d96fa1498ac0961c3e
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 71%

---

# 产品

`products` 变量会跟踪与其关联的产品和属性。此变量通常在单个产品页面、购物车页面和购买确认页面上设置。它是一个多值变量，这意味着您可以在同一次点击中发送多个产品，Adobe 会将该值解析为单独的维度项目。

>[!NOTE]
>
>如果在点击中设置此变量，而没有 [`events`](events/events-overview.md) 变量，则[产品查看次数](/help/components/metrics/product-views.md)量度将递增 1。确保使用 `products` 变量对每次点击设置适当的事件。

## 使用Web SDK的产品

产品包括 [已映射Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在多个XDM字段下：

* 类别已映射到 `productListItems[].lineItemId`.
* 产品已映射到 `productListItems[].SKU` 或 `productListItems[].name`. 如果两个XDM字段都存在， `productListItems[].SKU` 中，将使用。
* 数量已映射到 `productListItems[].quantity`.
* 价格已映射到 `productListItems[].priceTotal`.
* 促销eVar被映射到 `productListItems._experience.analytics.customDimensions.eVars.eVar1` to `productListItems._experience.analytics.customDimensions.eVars.eVar250`，具体取决于您要绑定到产品的eVar。
* 促销事件被映射到 `productListItems[]._experience.analytics.event1to100.event1.value` to `productListItems._experience.analytics.event901to1000.event1000.value`，具体取决于您要绑定到产品的事件。 如果在其中一个字段中设置事件，则该事件会自动包含在 [事件](events/events-overview.md) 字符串。

>[!NOTE]
>
>`lineItemId` 必须作为自定义字段进行添加，因为它尚未成为标准Analytics事件架构的一部分。 Adobe计划将来添加一个专用的“类别”字段。

## 使用Adobe Analytics扩展的产品

Adobe Experience Platform数据收集中没有用于设置此变量的专用字段；但是，存在多个第三方扩展可提供帮助。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]以查看所有可用的扩展。
4. 搜索术语“product”，结果会显示若干可用于设置此变量的扩展。

您可以使用其中一个扩展，也可以按照下面的 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.products

`s.products` 变量是一个字符串，其中包含每个产品的多个分隔字段。在字符串中使用分号 (`;`) 分隔每个字段。

* **类别** （可选）：产品类别。 此字段的最大长度为 100 个字节。
* **产品名称**（必需）：产品的名称。此字段的最大长度为 100 个字节。
* **数量**（可选）：购物车中此产品的数量。此字段仅适用于具有购买事件的点击。
* **价格**（可选）：以小数表示的产品总价格。如果数量大于 1，则将价格设置为总价，而不是产品单价。调整此值的货币以与 [`currencyCode`](../config-vars/currencycode.md) 变量匹配。请勿在此字段中包含货币符号。此字段仅适用于具有购买事件的点击。
* **事件**（可选）：与产品绑定的事件。使用管道字符 (`|`) 分隔多个事件。有关更多信息，请参阅[事件](events/events-overview.md)。
* **eVar**（可选）：与产品绑定的推销 eVar。使用管道字符 (`|`) 分隔多个推销 eVar。有关更多信息，请参阅[推销 eVar ](evar-merchandising.md)。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

此变量在同一点击中支持多个产品。它对于购物车和包含多种产品的购买非常有用。整个 `products` 字符串的最大长度为 64K。在字符串中使用逗号 (`,`) 分隔每个产品。

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>从产品名称、类别和推销 eVar 值中去除所有分号、逗号和管道字符。如果产品名称包含逗号，则 AppMeasurement 会将其解析为新产品的开头。此错误解析会丢掉产品字符串的其余部分，导致维度和报表中的数据不正确。

## 示例

当省略字段并包含多个产品时，`products` 变量会非常灵活。这种灵活性可能会使您容易丢失分隔符，从而导致您的实施向 Adobe 发送错误数据。

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

如果使用 `digitalData` [数据层](../../prepare/data-layer.md)，则可通过 `digitalData.product` 对象阵列进行迭代：

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```
