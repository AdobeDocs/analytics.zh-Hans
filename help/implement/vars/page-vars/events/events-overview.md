---
title: events
description: 设置事件变量，该变量控制网站上的大多数指标。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# events

维度和指标是报表的重要组成部分。 该变 `events` 量负责收集您网站上许多指标的数据。

## Adobe Experience Platform Launch中的活动

您可以在配置Analytics扩展时（全局变量）或根据规则设置事件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“ [!UICONTROL 事件] ”部分。

提供以下几项功能：

* 下拉列表允许您选择要包括的活动
* 用于序列化的可选文本字段。 See [event serialization](event-serialization.md) for more information.
* 事件值的可选文本字段。 您可以为货币事件加入货币，或为非货币事件加入一个整数以多次增加货币。 例如，在下拉列 `event1` 表下选择并在此字段 `10` 中包括，报告 `event1` 中的值将增加10。
* 用于添加其他活动的按钮。 对于可包含在点击中的事件数，没有合理的限制。

## AppMeasurement和Launch自定义代码编辑器中的s.events

变 `s.events` 量是一个字符串，其中包含要包含在点击中的以逗号分隔的事件列表。 此变量没有字节限制，因此不会被截断。 有效的值包括：

* `event1` - `event1000`:自定义事件，根据需要设置。 在组织的解决方案设计文档中记录您使用每 [个活动的方式](../../../prepare/solution-design.md)。 可用事件的数量取决于贵组织的Analytics合同。 大多数非传统合同组织有1000个可用的自定义事件。 如果您不确定有多少自定义活动可供您使用，请与贵组织的客户经理联系。
* `purchase`:将“订单”量度增加1，并采用变量中设置的 `products` 值来计算“单位”和“收入”。 有关更 [多信息](event-purchase.md) ，请参阅购买活动。
* `prodView`:增加“产品查看次数”量度。
* `scOpen`:增加“购物车”量度。
* `scAdd`:增加“购物车加货”量度。
* `scRemove`:增加“购物车减货”量度。
* `scView`:增加“购物车查看次数”量度。
* `scCheckout`:增加“结帐”量度。

> [!TIP] 此变量区分大小写。 避免错误地使用事件值，以确保准确的数据收集。

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### 多次增量计数器事件

如果需要，可以多次计数自定义事件。 为字符串中的所需事件分配一个整数。 默认情况下，在报表包设置中创建的事件是计数器事件。

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

> [!NOTE] 计数器事件不支持货币或小数值。 将货币事件用于货币，或将数字事件用于小数值。

### 使用货币事件

您可以更改自定义事件以使用货币而不是整数。 如果报表包货币与变量不匹配，货币事件会自动转换为报表包 `currencyCode` 的货币。 它们有助于计算运费、折扣或退款。 如果要将该事件仅归因 `products` 于该产品，则可以在变量中设置货币事件。

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] 如果在变量和变量中设置 `events` 货币值， `products` 则使用中的货币 `events` 值。 避免在变量和变量中设置 `events` 货币 `products` 值。

### 使用数字事件

您可以更改接受小数值的自定义事件，而不是整数。 数字事件的行为与货币事件类似，但它们不使用货币兑换。 如果要将事件仅归因到该产 `products` 品，您可以在变量中设置数字事件。

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] 如果在变量和变量中都设 `events` 置了一个 `products` 数值，则使用中的 `events` 数值。 避免在变量和变量中设 `events` 置数 `products` 值。
