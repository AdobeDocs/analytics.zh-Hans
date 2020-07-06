---
title: eVar（销售）
description: 与单个产品关联的自定义变量。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 29%

---


# eVar（销售）

*本帮助页介绍如何实施销售eVar。 For information on how merchandising eVars work as a dimension, see[eVars (Merchandising)](/help/components/dimensions/evar-merchandising.md)in the Components user guide.*

## 在报表包设置中设置 eVar

在实施中使用eVar之前，请确保在报表包设置中将eVar配置为所需的语法。 请参阅管理员指南中的[转化变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

>[!IMPORTANT]
>
>未正确配置推销eVar将导致变量出现意外值或数据丢失。 确保为您的实施正确配置了它。

## 使用产品语法实现

When &#39;Product Syntax&#39; is enabled, the merchandising category is populated directly within the `products` variable, so selecting and setting a binding event is not required. 推荐使用此方法，除非当发生成功事件时无法在 `products` 中设置此值。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

其值 `eVar1` 已分配给产品。 所有与本产品相关的后续成功事件将计入eVar值。

## 使用转换变量语法实现

Conversion Variable Syntax is used when the eVar value is not available to set in the `products` variable. 此方案通常意味着您的页面没有销售渠道或查找方法的上下文。 在这些情况下，您在到达产品页面之前设置销售变量，该值会一直存在，直到出现绑定事件。

当在配置期间选择捆绑事件时，eVar 的这个持久值将与该产品关联。For example, if `prodView` is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. 只有后续捆绑事件才能更新已分配给产品的促销 eVar。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

该值 `"Aviary"` 被 `eVar1` 分配给产品 `"Canary"`。 所有后续与本产品相关的成功事件均计入 `"Canary"`中。 另外，促销变量的当前值将被绑定到所有后续产品，直到满足以下其中一个条件为止：

* eVar过期（基于“过期时间”设置）
* 促销 eVar 被新值覆盖。
