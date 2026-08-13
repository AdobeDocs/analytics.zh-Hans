---
title: 购买事件
description: 使用购买事件收集“订单数”、“件数”和“收入”量度的数据。
feature: Appmeasurement Implementation
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/r-L330P6HA5qWBmEW-2LwECo-d3dhVK1ovWsfraErXE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 66%

---

# 购买事件

购买事件是 `events` 变量中的一个值。 对于希望收集网站所产生的收入相关数据的组织，此值非常有用。 它在很大程度上取决于 [`products`](../products.md) 和 [`purchaseID`](../purchaseid.md) 变量。

在设置购买事件时，它会影响以下量度：

* “订单数”量度每次递增 1
* “件数”量度每次递增 `products` 变量中的产品数
* “收入”量度每次递增 `products` 变量中价格参数之和

>[!NOTE]
>
>收入不是乘以数量字段。 例如，`s.products="Womens;Socks;5;4.50"`不会向收入传递$22.50，而是传递$4.50。 确保您的实施传递了所列数量的总收入。 例如，`s.products="Womens;Socks;5;22.50"`。

## 使用Web SDK设置购买事件

如果使用&#x200B;[**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，则购买事件使用以下XDM字段：

* 订单将映射到 `xdm.commerce.purchases.value`。
* 件数将映射到所有 `xdm.productListItems[].quantity` 字段的总和。 有关详细信息，请参阅[`products`](../products.md)。
* 收入将映射到所有 `xdm.productListItems[].priceTotal` 字段的总和。

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

如果使用&#x200B;[**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，则购买事件将按照AppMeasurement字符串语法使用`data.__adobe.analytics.events`。

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## 使用Adobe Analytics扩展设置购买事件

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 事件]部分，并将[!UICONTROL 事件]下拉列表设置为[!UICONTROL 购买]。

其他因变量（如`products`和`purchaseID`）在Adobe Experience Platform数据收集的Analytics扩展中没有专用字段。 对这些变量使用遵循 AppMeasurement 语法的自定义代码编辑器。

## 在AppMeasurement和Analytics扩展自定义代码编辑器中设置购买事件

购买事件是设置为 event 变量一部分的字符串。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 购买事件重复数据删除

当您触发购买事件时，Adobe 会检查以下各项：

* 点击是否包含 `purchaseID` 变量？ 如果不包含，Adobe 将使用点击中的信息创建“临时购买 ID”。 此临时购买 ID 仅适用于点击对应的访客。 每个报表包为每个访客 ID 存储先前 5 个临时购买 ID。
* 临时购买 ID 是否与存储的最近五个临时购买 ID 中的任意一个 ID 相匹配？ 如果是，则会将图像请求视为重复购买。 所有转化变量（包括购买事件）都不会出现在报表中。
* 如果定义了 `purchaseID` 变量，它是否与报表包中已收集的所有访客的任何值匹配？ 如果是，则会将图像请求视为重复购买。 所有转化变量（包括购买事件）都不会出现在报表中。
