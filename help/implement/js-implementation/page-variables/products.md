---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# 产品

 变量用于跟踪产品和产品类别，以及购买数量和购买价格。products 通常与购物车事件或 事件一起设置。

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>2016 年 1 月，我们更新了自动设置 *`prodView`* 事件的逻辑，当具有 *`product`* 但没有 *`event`* 时会执行此逻辑。此更新可能会导致 *`prodView`事件增加。**`prodViews`*&#x200B;仅在以下情况下增加：
>
>1. events 变量只包含无法识别的事件，例如 *`shoppingCart`* 或 *`cart`*，这些都不是有效事件。
   >
   >
1. *`products`* 变量不为空。
>
>
可能出现的副作用是由 *`prodView`* 事件触发的促销 eVar 可能与空的 *`product`* 相关联，但仅当 *`product list`* 只包含无效产品时（例如列出的产品中没有分号）才会出现这种情况。

*`products`* 变量可跟踪用户与网站产品的交互情况。例如，products 变量可跟踪产品被查看、添加到购物车、结帐以及购买的次数。它也可跟踪网站上促销类别的相对效果。以下方案是 products 变量的常见使用方式。

The *`products`*&#x200B;变量应始终结合成功事件进行设置。

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大大小 </th> 
   <th class="entry"> 调试程序参数 </th> 
   <th class="entry"> 填充报表 </th> 
   <th class="entry"> 默认值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>“<span class="wintitle"> products </span>”字符串的最大大小为 64 k。 </p> </td> 
   <td> 产品 </td> 
   <td> 产品 <p>类别（可选） </p> <p>收入（可选） </p> <p>件数（可选） </p> <p>自定义事件（可选） </p> <p>eVar（可选） </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**语法** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| 字段 | 定义 |
|---|---|
| 类别 | 包含关联的产品类别。在版本 15 中，products 可以与多个类别相关联，从而修复了版本 14 中存在的限制。如果之前未记录产品类别，则建议开始为版本 15 上的报表包填充此字段。 |
| 产品 | （必需）用于跟踪产品的标识符。此标识符用于填充[!UICONTROL 产品]报表。请务必在整个结帐过程中使用同一标识符。 |
| 数量 | 所购买的件数。此字段必须在[!UICONTROL 购买]事件中设置才能记录。 |
| 价格 | 指总购买量的联合成本（件数 x 单价），而不是单价。此字段必须在[!UICONTROL 购买]事件中设置才能记录。 |
| 事件 | 与指定产品关联的货币事件。请参阅[产品特定的货币事件](/help/implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C)和[订单范围的货币事件](/help/implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0)。 |
| eVar | 与特定产品关联的促销 eVar 值。请参阅[促销变量](/help/components/c-variables/c-merch-variables/var-merchandising.md)。 |

包含在&#x200B;*`products`*&#x200B;变量中包含的值基于您所记录的事件类型。省略类别时，需要使用类别/产品分隔符 (;) 作为占位符。仅当需要区分所包含的参数时，才要求使用其他分隔符，如本页上的示例所示。

**设置非购买事件的 products** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

*`products`* 变量必须结合成功事件进行设置。

**设置购买事件的 products** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

*`purchase`* 事件应在订购流程的最终确认（“谢谢！”）页面上设置。产品名称、类别、数量和价格都将使用 *`products`* 变量捕获。尽管 *`purchaseID`* 并非必要变量，但是强烈建议设置此变量，以防出现重复订购情况。

**产品特定的货币事件** {#section_F814DF053C0D463A97DA039E6323720C}

如果货币事件在 *`products`* 变量中接收的是一个值而不是 events 变量，则该事件仅适用于该值。这对于跟踪产品特定的折扣、产品运输及类似值非常有用。例如，如果将事件 1 配置为跟踪产品运输，则运输费用为“4.50”的产品可能会类似于以下内容：

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

在此示例中，值 4.50 直接与“Running Shoes”产品相关联。如果将 event1 添加到 products 报表中，您会发现“Running Shoes”行项目将列出“4.50”。与“价格”类似，该值应反映所列数量的总值。如果有 2 个运输费用均为“4.50”的项目，则 event1 应为“9.00”。

**订单范围的货币事件** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

如果货币事件在事件列表中接收的是值而不是 *`products`* 变量，则它将适用于 *`products`* 变量中的所有产品。这对于在不修改产品价格，或单独跟踪产品列表中值的情况下，跟踪订单范围折扣、运输费以及类似值非常有用。

例如，如果将 event10 配置为包含订单范围的折扣，则折扣为 10% 的购买可能会类似于以下内容：

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

在货币事件报表中，报表合计表示去除重复后的事件总数（在本示例中为报表期间的总折扣数），而不是每个产品的事件值总数。例如，您会发现“Running Shoes”和“Running Socks”都列为“9.95”，而总值也为“9.95”。

> [!NOTE]如果在 *`products`* 变量和 *`events`* 变量中指定了相同数值/货币事件的值，则会使用 *`events`* 的值。

**缺陷、问题和提示** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* *`products`* 变量应当始终结合一个[!UICONTROL 成功]事件（或多个事件）进行设置。如果未指定任何[!UICONTROL 成功]事件，则默认事件为 [!UICONTROL prodView]。

* 在填充 products 变量之前，请先清除产品和类别名称中的所有逗号和分号。
* 清除所有 HTML 字符（注册符号、商标等）。
* 清除价格中的货币符号 ($)。

**示例** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

