---
description: products 变量用于跟踪产品和产品类别（以及购买数量和购买价格）。
keywords: Analytics 实施;产品变量;产品查看;成功事件
seo-description: products 变量用于跟踪产品和产品类别（以及购买数量和购买价格）。
seo-title: 详细的产品查看页面
solution: Analytics
title: 详细的产品查看页面
topic: 开发人员和实施
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 详细的产品查看页面

products 变量用于跟踪产品和产品类别（以及购买数量和购买价格）。

成功事件应始终与 *`products`* 变量一起设置。

```js
s.events="prodView"
```

>[!NOTE]
>
>尽管实施中的 *`prodView`* 处理方式与事件相同，但其在界面中的灵活性却不相同。*`prodView`*事件是产品的一个实例，只能在 *`products`* 报表中使用。除 *`prodView`* 事件之外，Adobe 还建议使用 *`custom`* 事件。这样，便可以同时查看产品查看量度和其他转化报表中的其他量度。

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>产品字符串语法必须以分号开头。这是一项传统的语法要求。以前，分号是用来分隔类别和产品的，但在您要更改对产品的分类方式时，这会在界面中造成一定的限制。为了在报表中实现最大的灵活性，最好将此保留为空，并使用分类来设置类别。

## 购物车页面（scOpen、scAdd、scRemove）{#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## 首次结帐页面 {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=”;SKU" 
```

## 确认页面 {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>虽然在产品字符串中使用 SKU 可能会降低 *`products`* 报表的可读性，但是在以后要对产品进行分类时，它可提供最大的灵活性。您可以从 SKU 创建表示完成、制造商、类别和子类别的类别。

*`products`*&#x200B;变量与 *`purchase`事件一起进行设置时，以上所示的产品值中将包含购买数量和总购买价格。*
