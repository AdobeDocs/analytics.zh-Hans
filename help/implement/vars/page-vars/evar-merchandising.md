---
title: eVar（推销）
description: 与单个产品关联的自定义变量。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '355'
ht-degree: 100%

---


# eVar（推销）

*此帮助页面介绍了如何实施推销 eVar。有关推销 eVar 如何用作维度的信息，请参阅组件用户指南中的 [eVar（推销）](/help/components/dimensions/evar-merchandising.md)。*

## 在报表包设置中设置 eVar

在实施中使用 eVar 之前，请确保在报表包设置中将 eVar 配置为所需的语法。请参阅管理员指南中的[转化变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

>[!IMPORTANT]
>
>未能正确配置推销 eVar 会导致变量出现意外值或数据丢失。确保为您的实施正确配置推销 eVar。

## 使用产品语法实施

启用“产品语法”后，将直接在 `products` 变量内填充推销类别，因此无需选择和设置捆绑事件。推荐使用此方法，除非当发生成功事件时无法在 `products` 中设置此值。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

`eVar1` 的值已分配给产品。所有与本产品相关的后续成功事件将计入 eVar 值。

## 使用转化变量语法实施

如果在 `products` 变量中无法设置 eVar 值，应使用转化变量语法。这种情况通常意味着您的页面没有推销渠道的任何上下文或查找方法。在这类情况下，请先设置推销变量，然后再进入产品页，该值会持续到捆绑事件发生为止。

当在配置期间选择捆绑事件时，eVar 的这个持久值将与该产品关联。例如，如果 `prodView` 指定为捆绑事件，那么只有当该事件发生时，推销类别才会与当前产品列表绑定。只有后续捆绑事件才能更新已分配给产品的推销 eVar。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

`eVar1` 的值 `"Aviary"` 已分配给产品 `"Canary"`。所有与本产品相关的后续成功事件将计入 `"Canary"`。另外，推销变量的当前值将被绑定到所有后续产品，直到满足以下其中一个条件为止：

* eVar 过期（根据“过期时间”设置）
* 推销 eVar 被新值覆盖。
