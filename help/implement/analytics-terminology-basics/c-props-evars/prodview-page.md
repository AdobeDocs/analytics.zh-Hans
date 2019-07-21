---
description: products 变量用于跟踪产品和产品类别（以及购买数量和购买价格）。
keywords: Analytics实施；products变量；产品视图；success事件
seo-description: products 变量用于跟踪产品和产品类别（以及购买数量和购买价格）。
seo-title: 详细产品查看页面
solution: Analytics
title: 详细产品查看页面
topic: 开发人员和实施
uuid: 464c9daf-b042-4fb8-8ca6-e104 c0 bcf45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 详细产品查看页面

products 变量用于跟踪产品和产品类别（以及购买数量和购买价格）。

A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

>[!NOTE]
>
>*`prodView`* 在执行像事件一样的过程中，它在界面中的灵活性不相同。The *`prodView`*event is an instance of the product and is only available in the *`products`* report. Adobe recommends you use a *`custom`* event in addition to the *`prodView`* event. 这样，便可以同时查看产品查看量度和其他转化报表中的其他量度。

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>products字符串语法必须以分号开头。这是一项传统的语法要求。以前，分号是用来分隔类别和产品的，但在您要更改对产品的分类方式时，这会在界面中造成一定的限制。为了在报表中实现最大的灵活性，最好将此保留为空，并使用分类来设置类别。

## Shopping Cart Page ( scOpen , scAdd , scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

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
>While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. 您可以从 SKU 创建表示完成、制造商、类别和子类别的类别。

当&#x200B;*`products`*&#x200B;变量与 *`purchase`事件一起进行设置时，以上所示的产品值中将包含购买数量和总购买价格。*
