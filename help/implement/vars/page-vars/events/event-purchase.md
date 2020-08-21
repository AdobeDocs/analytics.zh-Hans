---
title: 购买事件
description: 使用购买事件收集“订单数”、“件数”和“收入”量度的数据。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---


# 购买事件

购买事件是 `events` 变量中的一个值。对于希望收集网站所产生的收入相关数据的组织，此值非常有用。它在很大程度上取决于 [`products`](../products.md) 和 [`purchaseID`](../purchaseid.md) 变量。

在设置购买事件时，它会影响以下量度：

* “订单数”量度每次递增 1
* “件数”量度每次递增 `products` 变量中的产品数
* “收入”量度每次递增 `products` 变量中价格参数之和

>[!NOTE]
>
>收入不是乘以数量字段。例如，`s.products="Womens;Socks;5;4.50"` 不会向收入传递 $22.50，而是传递 $4.50。请确保您的实施传递了所列数量的总收入。例如：`s.products="Womens;Socks;5;22.50"`。

## 在 Adobe Experience Platform Launch 中设置购买事件

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 事件]部分，然后将事件下拉列表设置为[!UICONTROL 购买]。

其他因变量（例如 `products` 和 `purchaseID`）在 Launch 中没有专用字段。对这些变量使用遵循 AppMeasurement 语法的自定义代码编辑器。

## 在 AppMeasurement 和 Launch 自定义代码编辑器中设置购买事件

购买事件是设置为 event 变量一部分的字符串。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 购买事件重复数据删除

当您触发购买事件时，Adobe 会检查以下各项：

* 点击是否包含 `purchaseID` 变量？如果不包含，Adobe 将使用点击中的信息创建“临时购买 ID”。此临时购买 ID 仅适用于点击对应的访客。每个报表包为每个访客 ID 存储先前 5 个临时购买 ID。
* 临时购买 ID 是否与存储的最近五个临时购买 ID 中的任意一个 ID 相匹配？如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。
* 如果定义了 `purchaseID` 变量，它是否与报表包中已收集的所有访客的任何值匹配？如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。
