---
description: 描述实例如何在促销变量上进行计数。
keywords: Analytics 实施
seo-description: 描述实例如何在促销变量上进行计数。
seo-title: 销售变量上的实例
solution: Analytics
title: 销售变量上的实例
topic: 开发人员和实施
uuid: 4cdfd53e-88aa-48cf-a135-98f7 fc8 dcc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 销售变量上的实例

描述实例如何在促销变量上进行计数。

实例当前不支持促销变量。如果您注意到报表中的实例包含促销变量，则表示此 eVar 是在产品字符串以外的某些位置设置的，并且不应该把此变量视为选中的促销变量的实例。

如果您使用转化变量语法，那么每次设置变量时都会计算实例。但是，该实例应当归于“无”，除非每次设置变量时发生如下情况：

* 已设置捆绑事件。
* 已设置产品变量。
* 促销 eVar 包含值。

例如，eVar1 的以下实例被分配给“户外：滑雪镜”：

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

但是，在下一个示例中，eVar1 的实例会被分配给“无”，因为设置 eVar 时所有条件均未满足（既没有捆绑事件，也没有设置产品变量）：

访问的页面 1：

```js
s.eVar1="Outdoors:Ski Goggles"
```

访问的页面 2：

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

如果您在未发生捆绑事件的页面上为 eVar 设置了一个值，或者在没有捆绑事件的产品字符串中设置了一个 eVar 值，则会被分配至“无”。

>[!NOTE]
>
>对销售变量上的计数实例的当前功能正在进行审核，计划在即将发布的版本中更改。

