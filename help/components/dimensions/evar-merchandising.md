---
title: eVar（销售）
description: 与产品维关联的自定义变量。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 25%

---


# eVar（销售）

*本帮助页介绍销售eVar如何作为维度工作。 For information on how to implement merchandising eVars, see[eVars](/help/implement/vars/page-vars/evar.md)in the Implement user guide.*

测量外部促销活动或外部搜索术语的成功程度时，通常需要一个单独的值来对发生的所有成功事件接收信用。例如，如果某个客户单击电子邮件促销活动中的链接访问您的网站，那么该客户因此进行的所有购买都将计入此促销活动中。

当客户查找多个项目时，由内部搜索或类别浏览驱动的事件会如何？ For example, a customer searches your site for `"goggles"`, then adds a pair to their cart:

![护目镜示例](assets/merch-example-goggles.png)

Before checkout, the customer searches for `"winter coat"`, then adds a down jacket to the to their cart:

![外套示例](assets/merch-example-coat.png)

当访客完成此购买时，您将进行内部搜索 `"winter coat"` 以计入购买一对护目镜（假定eVar使用默认的“最近”分配）。 Good for `"winter coat"`, but bad for marketing decisions:

| 内部搜索词 | 收入 |
|---|---|
| 冬衣 | $157 |

## 促销变量如何解决此问题

销售eVar允许您在成功事件发生时将eVar的当前值分配给产品。 此值将始终与该产品绑定，即使这个特定的 eVar 以后设置了一个或多个新的值也不例外。

If merchandising is enabled for the eVar in the previous example, the search term `"goggles"` is tied to the snow goggles, and the search term `"winter coat"` is tied to the down jacket. 销售电子变量按产品层分配收入，因此每个术语都会收到与术语关联的产品的收入金额的贷记：

| 内部搜索词 | 收入 |
|---|---|
| 冬衣 | $119 |
| 护目镜 | $38 |

有关实 [施说明](/help/implement/vars/page-vars/evar-merchandising.md) ，请参阅销售eVar。

## 有关促销变量的实例

不建 [议](../metrics/instances.md) “实例”量度用于推销变量。

* 对于使用产品语法的销售变量，实例根本不会增加。
* 对于使用转换变量语法的推销变量，每次设置eVar时都会计算实例。 但是，它属于维项，除 `"None"` 非同一次点击发生以下所有情况：
   * 销售eVar设置有值。
   * 变 `products` 量用值定义。
   * 已设置捆绑事件。

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

由于转换变量语法的大多数用例要求eVar和products变量在不同的点击量上，因此使用“实例”量度是不现实的。
