---
title: events
description: 设置事件变量，该变量可控制网站上的大多数量度。
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '680'
ht-degree: 100%

---

# events

维度和量度是报表的重要组成部分。`events` 变量负责收集您网站上许多量度的数据。事件通常会递增报表中的[量度](/help/components/metrics/overview.md)。

在实施事件之前，请确保在报表包设置的[成功事件](/help/admin/admin/c-success-events/success-event.md)下创建和配置事件。如果您计划在链接跟踪点击中使用自定义事件，请确保正确设置 [`linkTrackVars`](../../config-vars/linktrackvars.md) 和 [`linkTrackEvents`](../../config-vars/linktrackevents.md)。

## 使用 Adobe Experience Platform 中的标记的“事件”

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置事件。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 事件]部分。

可使用以下几项功能：

* 允许您选择要包括的事件的下拉列表
* 用于序列化的可选文本字段。请参阅[事件序列化](event-serialization.md)以了解更多信息。
* 用于事件值的可选文本字段。您可以包含货币（货币事件）或整数（非货币事件）以使其多次递增。例如，在下拉列表下选择 `event1` 并在此字段中包含 `10`，报表中的 `event1` 将以 10 为单位进行递增。
* 用于添加其他事件的按钮。对于可包含在点击中的事件数，没有相应的限制。

## AppMeasurement 和自定义代码编辑器中的 s.events

`s.events` 变量是一个字符串，其中包含要包含在点击中的以逗号分隔的事件列表。此变量没有字节限制，因此不会被截断。有效的值包括：

* `event1` - `event1000`：自定义事件，根据需要进行设置。在贵组织的[解决方案设计文档](../../../prepare/solution-design.md)中记录如何使用每个事件。可用事件的数量取决于贵组织的 Analytics 合同。大多数使用非传统合同的组织具有 1,000 个可用的自定义事件。如果您不确定有多少自定义事件可供使用，请与贵组织的客户经理联系。
* `purchase`：将[“订单”](/help/components/metrics/orders.md)量度以 1 为单位递增，并采用 `products` 变量中设置的值来计算[“件数”](/help/components/metrics/units.md)和[“收入”](/help/components/metrics/revenue.md)。有关更多信息，请参阅[购买事件](event-purchase.md)。
* `prodView`：增加[“产品查看次数”](/help/components/metrics/product-views.md)量度。
* `scOpen`：增加[“购物车”](/help/components/metrics/carts.md)量度。
* `scAdd`：增加[“购物车加货”](/help/components/metrics/cart-additions.md)量度。
* `scRemove`：增加[“购物车减货”](/help/components/metrics/cart-removals.md)量度。
* `scView`：增加[“购物车查看次数”](/help/components/metrics/cart-views.md)量度。
* `scCheckout`：增加[“结帐”](/help/components/metrics/checkouts.md)量度。

>[!NOTE]
>
>此变量区分大小写。请避免错误地将事件值的首字母大写，以确保进行准确的数据收集。

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### 多次增加计数器事件

如果需要，可以多次计算自定义事件。为字符串中的所需事件分配一个整数。默认情况下，在报表包设置中创建的事件是计数器事件。

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>计数器事件不支持货币或小数值。请将货币事件用于货币，或将数值事件用于小数值。

### 使用货币事件

您可以更改自定义事件以使用货币而不是整数。如果报表包货币与 `currencyCode` 变量不匹配，货币事件会自动转换为报表包的货币。它们有助于计算运费、折扣或退款。如果要将货币事件仅归因于该产品，则可以在 `products` 变量中设置该事件。

在实施货币事件之前，请确保在报表包设置的[成功事件](/help/admin/admin/c-success-events/success-event.md)下将所需事件设置为“货币”。

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>如果同时在 `events` 变量和 `products` 变量中设置货币值，则会使用 `events` 中的货币值。避免同时在 `events` 变量和 `products` 变量中设置货币值。

### 使用数值事件

您可以更改自定义事件以接受小数值而不是整数。数值事件的行为与货币事件类似，只是它们不使用货币换算。如果要将数值事件仅归因于该产品，您可以在 `products` 变量中设置该事件。

在实施数值事件之前，请确保在报表包设置的[成功事件](/help/admin/admin/c-success-events/success-event.md)下将所需事件设置为“数值”。

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>如果同时在 `events` 变量和 `products` 变量中设置数值，则会使用 `events` 中的数值。避免同时在 `events` 变量和 `products` 变量中设置数值。
