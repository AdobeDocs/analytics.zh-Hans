---
description: 描述如何启用和实施促销变量。
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
title: 实施促销变量
topic: Developer and implementation
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 实施促销变量

描述如何启用和实施促销变量。

## 启用促销变量

可以在&#x200B;**[!UICONTROL 管理工具]** > **[!UICONTROL 报表包]** > **[!UICONTROL 转化变量]**&#x200B;下为任何自定义 eVar 启用促销。

![](assets/merch-enable.png)

| 设置 | 描述 |
|--- |--- |
| 过期时间 | 确定促销值的持续时间。 |
| 促销 | **产品语法：**&#x200B;该值在 `s.products` 内设置。<br>**转化变量语法：**该值在指定的促销 eVar 中设置。 |
| 促销捆绑事件（仅转化变量语法） | 指示何时将产品与当前的促销类别绑定。通过按住 Ctrl 并单击列表中的多个项目，可选择多个事件。只有在选择了“转化变量语法”后才能选择事件。 |

## 使用产品语法实施

启用产品语法后，将直接在产品变量内部填充促销类别，因此无需选择和设置捆绑事件。推荐使用此方法，除非当发生成功事件时无法在 `s.products` 中设置此值。

### 语法

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### 示例

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

eVar1 的值“护目镜”被分配给产品“雪地护目镜”。所有涉及此产品的后续成功事件（产品添加、结账、购买等）都将被归为“护目镜”。

## 使用转化变量语法实施

在 `s.products` 中无法设置 eVar 值时应使用转化变量语法。这通常意味着您的页面没有促销渠道的任何上下文或查找方法。在这类情况下，必须先设置促销变量，然后再进入产品页，该值会持续到捆绑事件发生为止。

当在配置期间选择捆绑事件时，eVar 的这个持久值将与该产品关联。例如，如果 prodView 指定为捆绑事件，那么只有当该事件发生时，促销类别才会与当前产品列表绑定。只有后续捆绑事件才能更新已分配给产品的促销 eVar。

### 语法

放在捆绑事件的同一页面或前一页面上：

```js
s.eVar1="merchandising_category";
```

放在捆绑事件发生的页面上：

```js
s.events="prodView";
s.products="category;product";
```

### 示例

在访问的页面 1 上：

```js
s.eVar1="Outdoors"
```

在访问的页面 2 上：

```js
s.events="prodView";
s.products=";Snow Goggles";
```

eVar1 的值“户外”被分配给产品“雪地护目镜”。所有涉及此产品的后续成功事件（产品添加、结账、购买等）都将被归为“雪地护目镜”。另外，促销变量的当前值将被绑定到所有后续产品，直到满足以下其中一个条件为止：

* eVar 过期（根据“过期时间”设置）
* 促销 eVar 被新值覆盖。

## 其他外部信息

[!DNL analyticsdemystified.com] 上的[高级转化语法促销](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/)
